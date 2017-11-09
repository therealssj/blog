+++
title = "CX Übersicht"
tags = [
    "CX",
]
bounty = 20
date = "2017-09-06"
categories = [
    "Overview",
]
+++

<!-- MarkdownTOC autolink="true" bracket="round" depth="2" -->

- [Einführung in CX](#cx-introduction)
- [Repository des Projekts](#projects-repository)
- [Syntax](#syntax)
- [Affordanz](#affordances)
    - [Aritätsrestriktionen](#arity-restrictions)
    - [Typrestriktionen](#type-restrictions)
    - [Existentialrestriktionen](#existential-restrictions)
    - [Bezeichnerrestriktionen](#identifier-restrictions)
    - [Grenzrestriktionen](#boundaries-restrictions)
    - [Userdefinierte Restriktionen](#user-defined-restrictions)
- [Striktes Typisierungssystem](#strict-typing-system)
- [Kompiliert und Interpretiert](#compiled-and-interpreted)
    - [Lesen-Evaluieren-Ausgeben Schleife](#read-eval-print-loop)
    - [Meta-Programmierung Kommandos](#meta-programming-commands)
    - [Stufung](#stepping)
    - [Interaktives Debugging](#interactive-debugging)
- [Integrierte evolutionäre Algorithmen](#integrated-evolutionary-algorithm)
- [Serialisierung](#serialization)

<!-- /MarkdownTOC -->

# Einführung in CX

CX ist beides, eine Spezifikationssprache und eine Programmiersprache, designt um ein neues 
Paradigma, basierend auf dem Konzept der Affordanz zu begrüßen.
Affordanzen erlauben es einem Programm zu wissen, welche Aktionen ausgeführt werden können
und welche nicht. Zum Beispiel können wir das Programm fragen, welche Argumente einer Funktion
mitgegeben werden können und das Programm antwortet mit einer Liste der möglichen Aktionen.
Nachdem entschieden wurde, welche Aktion der Liste angebracht ist, können wir eine der Aktionen 
wählen und das Programm wird die gewählte Aktion anwenden. Konsequenz des CXs Affordanzsystems 
ist die Erstellung eines genetisches Programmieralgorithmus, der angeborene Funktion bereitgestellt wird 
und genutzt werden kann, um die Programmstruktur während der Laufzeit zu optimieren. 

Die CX-Spezifikation besagt, dass dem Programmierer ein Compiler sowie ein Interpreter zugänglich
sein müssen. Der Interpreter kann leicht durch eine Lesen-Evaluieren-Ausgeben-Schleife aufgerufen 
werden, in der der Programmierer interaktiv Elemente dem Programm hinzufügen und entfernen kann.
Nachdem das Programm beendet ist kann es kompiliert werden, um dessen Performance zu verbessern.

Die Typisierung in CX ist sehr strikt. Das einzige "implizite Casting" tritt auf, wenn der Parser 
bestimmt was ein Integer ist, ein Float, ein Boolean, ein String oder ein Array. Wenn zum Beispiel 
eine Funktion einen 64 Bit Integer als Eingabeparameter benötigt, muss man explizit mittels
einer Cast-Funktion zum geforderten Typ konvertieren.

Zu guter Letzt kann ein CX-Programm vollständig in Byte-Arrays serialisiert werden,
was es seinen Ausführungszustand und seine Struktur behalten lässt. Diese serialiserte 
Version eines Programmes kann später deserialisiert werden, um die Ausführung, auf einem 
beliebigen Gerät mit CX Interpreter/Compiler, fortzusetzen.

Die folgenden Abschnitte gehen auf die oben besprochenen CX-Features detaillierter ein.

# Repository des Projekts

Der Quellcode des Projekts kann aus seinem Github-Repository heruntergeladen werden:
[https://github.com/skycoin/cx](https://github.com/skycoin/cx). 
Das Repository enthält die Spezifikationsdatei, Dokumentation, Beispiele und natürlich
den Quellcode selbst.

# Syntax

Wie schon in der Einführung erwähnt ist CX zugleich Spezifikations-, als auch Programmiersprache. 
Die CX-Spezifikation verhängt keine Syntax, sondern die Strukturen und Prozesse, welche ein CX-Dialekt 
implementieren muss um als CX erachtet zu werden.
Das hat zur Konsequenz, dass man zwei CX-Dialekte implementieren kann, einen mit einer lisp-ähnlichen
Syntax und einen anderen mit c-ähnlicher Syntax. Diese zugrundeliegende Sprache wird CX-Base genannt,
oder auch "die Basissprache". In diesem Dokument wird eine Implementation genutzt, um die Möglichkeiten
der Spezifikation zu präsentieren, obwohl deren Zweck nicht nur das dienen als akademisches Tool ist, 
sondern sie soll eine vollständige und robuste Sprache für universale Anwendungen werden.

Die in diesem Dokument verwendete CX hat das Ziel eine Syntax aufzuweisen, welche der Syntax der 
Sprache Go so ähnlich wie nur möglich ist.

# Affordanzen

Ein Programmierer muss eine Plethora von Entscheidungen während der Konstruktion eines Programmes 
treffen, beispielweise unter anderen wie viele Parameter eine Funktion erhält, wie viele Parameter sie 
zurückgibt, welche Statements benötigt werden um die gewünschte Funktionalität zu erhalten und
welche Argumente dieser Statement-Funktion als Parameter mitgegeben werden müssen. Das Affordanzsystem
in CX kann befragt werden, um eine Liste der möglichen Aktion, die auf einem Element angewandt werden können,
zu erhalten. In diesem Kontext stehen Elemente für Funktionen, Strukturen (structs), Module und 
Ausdrücke (expressions).

Ohne einen Satz von Regeln und Fakten zu haben, die diktieren was der Zweck und die Logik hinter einem
Programm sein müssen, kann man jedoch einige einfache Einschränkungen bestimmen, welche zumindest die
semantisches Korrektheit eines Programms garantieren. Das Affordanzsystem stellt solche Einschränkungen
als erste Filterschicht bereit und wird unten näher beschrieben.

### Aritätsrestriktionen

Ausrücke in CX können mehrere Werte zurückgeben. Dies kreiert eine Herausforderung für das Affordanzsystem,
da die Anzahl an Variablen, welche die Ausgabenargumente eines Ausdrucks erhält, der Anzahl der Ausgaben,
die durch den Operator des Ausdrucks definiert werden, entsprechen muss. 

```
out1, out2, ..., outN := op(inp1, inp2, ..., inpM)
```

Wenn das obige Bespiel korrekt ist, dann muss *op* Argumente in der Anzahl von *N* zurückgeben. 
Dieses Problem wird noch schwieriger, wenn wir bedenken das die Definition von *op* vom 
Affordanzsystem selbst, oder vom User, zukünftig geändert werden könnte: Sobald sich die Definition
von *op* verändert, können neue Affordanzen zu jedem Ausdruck, der *op* als Operator verwendet, angewendet
werden, weil die Anzahl der erwarteten Ausgabevariablen von *op* nun nicht mehr mit den tatsächlich ausgebenen
übereinstimmen.

Die bisherige Logik impliziert ebenso, dass wenn die Anzahl der eingehenden Variablen gleich der Anzahl der 
Ausgabeparameter des Operators des Ausdrucks ist, die Aktion des weiteren Hinzufügens neuer eingehender 
Variablen nicht mehr ausgeführt werden kann.

Aritätsrestriktionen können ebenso auf Eingabeargumente von Ausdrücken angewendet werden, sprich ein 
Funktionsaufruf hat bereits alle seine Eingabeargumente festgelegt, dann sollte das Affordanzsystem 
als potentielle Aktion keine weiteren Argumente zum Hinzufügen einberufen. Gleichermaßen sollte das 
Affordanzsystem, sofern befragt worden, dem Programmierer mitteilen, dass das Hinzufügen von neuen 
Argumenten zum Funktionsaufruf möglich ist, sofern ein Ausdruck versucht einen Operator mit weniger als den benötigten Argumenten aufzurufen.

**Beispiel:**

*Vermerk: String-Verknüpfungen wurden noch nicht implementiert. Ebenso fügt die Print-Funktion
stets eine neue Zeile an das Ende des ausgegebenen Strings an. Eine zukünftige Version der 
CX-Implementation, die in diesem Dokument vorgestellt wird, adressiert diese Probleme.*

```
var age i32 = 18
var steps i32 = 23

func advance (direction str, numberSteps i32) () {
    printStr("Advancing:")
    printStr(direction)
    printStr("Number of steps:")
    printI32(numberSteps)
}

func main () () {
    advance("North")
}
```
Im obigen Beispiel fehlt dem Aufruf von *advance* in der *main*-Funktion ein Argument. 
Wenn man das Affordanzsystem befragt sollte dieses, unter anderen Dingen, Aktionen, ähnlich wie 
die Folgenden, anwerben:
```
...
(k)       AddArgument advance age
(k+1)     AddArgument advance steps
...
```

wobei k den arbiträren Index repräsentiert. Wie man erkenne kann, sagt das Affordanzsystem dem 
Programmierer, dass zwei der möglichen durchführbaren Aktionen, das Hinzufügen eines weiteren Arguments 
zur advance-Funktion ist, sowie das die globalen Definitionen *age*, *steps* als mögliche Argumente in Betracht
kommen.

Es ist bemerkenswert, dass die Affordanzen stets aufgezählt sein sollte und deren Ordnung sollte 
konstant über mehrere Aufrufe des Affordanzsystems bleiben. Der Grund dafür ist, dass der Programmierer
in der Lage sein sollte dem System anzugeben, welche Affordanz nach dem Begutachten der Befragung
angewendet werden soll.

### Typrestriktionen

Das übliche Verhalten von Programmiersprachen ist es, ein Typisierungssystem zu haben, welches den
Programmierer im Senden von unerwarteten Argumenten in Funktionsaufrufen einschränkt. 
Selbst in schwach-typisierten Programmiersprachen verursachen Operationen wie `true / "hello world"`
einen Error (außer natürlich im Falle einer [esoterischen Sprache](https://en.wikipedia.org/wiki/Esoteric_programming_language)). CX befolgt ein sehr 
[striktes Typisierungssystem](#strict-typing-system) und Argumente, welche nicht exakt dem erwarteten
Typen entsprechen, sollten nicht als Kandidaten für die Affordanzaktionen betrachtet werden (obwohl
ein Workaround wäre, diese Argumente in Cast-Funktionen einzuhüllen, bevor sie dem Affordanzsystem
gezeigt werden).

Typrestriktionen müssen auch beim Zuweisen eines neuen Wertes zu einer bereits existierenden Variable
bedacht werden. In CX muss eine Variable, die mit einem bestimmten Typ deklariert wurde, diesen Typ 
während ihrer gesamten Lebenszeit behalten (solange dieser nicht mittels meta-programmierungs Kommandos/
Funktionen entfernt wird und erneut deklariert wird). Deshalb sollte eine, als 32-Bit Integer deklarierte 
Variable nicht als Kandidat für das Erhalten eines 64-Bit Float Ausgabewerts in Betracht bezogen werden. 

### Existentialrestriktionen 

Dieser Typ von Restriktionen kann auf den ersten Blick trivial erscheinen: Wenn ein Element nicht 
existiert, sollte eine Affordanz, die des involviert, ebenso nicht existieren. Nichtsdestotrotz 
wird diese Restriktion zur Herausforderung, wenn wir eine Situation in Betracht ziehen, in der eine
Funktion umbenannt wurde und durchgehend durch ein Programm bereits als Operator in Ausdrücken 
verwendet wurde. Wenn das Programm in der Form seines Quellcodes ist, wird dieses Problem auf ein 
einfaches "Suchen & Ersetzen"-Problem reduziert, aber während der Laufzeit wird das Affordanzsystem
sehr nützlich: Eine Affordanz um die an diesen Operator gebundene Bezeichnung zu ändern.

Selbst wenn ein Element nicht umbenannt worden ist, ist das Bestimmen, ob ein Element existiert
oder nicht keinesfall trivial. Die in den Affordanzen zu verwendenen Elemente müssen auf dem 
Aufrufsstack gesucht werden und zwar innerhalb des aktuellen Scopes, des globalen Scopes und im 
Scope anderer Module.

### Bezeichnerrestriktionen

Das Hinzufügen von neu benannten Elementen sind übliche Kandidaten für Aktion von Affordanzen.
Eine Restriktion, welche beim Versuch solche Typen von Affordanzen anzuwenden, ist das sicherstellen 
einer eindeutigen Bezeichnung des neuen Elements, damit Redefinitionen umgangen werden. 
Das Affordanzsystem kann entweder innerhalb des Scopes des Elements eine eindeutige Bezeichnung
erstellen, oder den Programmierer nach einer angemessenen Bezeichnung fragen.

### Grenzrestriktionen

CX stellt standardmäßig Funktionen für das Zugreifen und Modifizieren von Elementen aus Arrays bereit.
Beispiele eines Array-Lesers (reader) und eines Array-Schreibers (writer) sind:

```
readI32([]i32{0, 10, 20, 30}, 3)
writeF32([]f32{0.0, 10.10, 20.20}, 1, 5.5)
```

Im ersten Ausdruck wird auf ein Array von vier 32-Bit Integern zugegriffen an der
Indexposition 3, welche das letzte Element des Arrays zurückgibt.
Im zweiten Ausdruck wird das zweite Element eines Arrays aus drei 32-Bit Floats 
auf den Wert 5.5 geändert. Wenn auf eines der beiden Arrays mit einem negativen Index
oder einem Index außerhalb der Länge des Arrays zugegriffen werden würde, würde ein
"außerhalb der Grenzen"-Error auftreten.

Wenn nur die Typrestriktionen befolgt werden, wird das Affordanzsystem dem Programmierer
sagen, dass ein beliebiges 32-Bit Integer Argument als Index verwendet werden kann, um auf
das Array zuzugreifen. Obwohl diese Programme kompilieren würden, sind "außerhalb der Grenzen"-Errors
sehr wahrscheinlich, außer der Programmierer würde dem ausgewählten Index für die Anwendung besondere
Aufmerksamkeit schenken.

Das Affordanzsystem muss die Affordanzen nach den folgenden Kriterien filtern:
Verwerfen von jeglichen negativen 32-Bit Integern, verwerfen von jeglichen 32-Bit Integern, welche
die Länge des Arrays überschreiten und an das Array als Array-Schreiber oder Array-Leser gesendet werden.

### Userdefinierte Restriktionen

*Vermerk: Das userdefinierte Restriktionssystem ist aktuell noch im Experimentierstadium.*

Die grundsätzlichen Restriktionen garantieren zumindest die Abwesenheit von Laufzeit-Errors.
Diese Restriktionen sollten genügen, um eine interessante System zu erstellen, sowie der CX
systemeigene [evolutionärer Algorithmus](#integrated-evolutionary-algorithm). Trotzdessen sind 
in einigen Situationen robustere Systeme notwendig. Für diese Zwecke werden Klauseln, Anfragen 
und Objekte genutzt, um die Umwelt eines Modules zu beschreiben. Diese Elemente werden über einen 
internen Prolog-Interpreter und die CX systemeigenen Funktionen *setClauses* (stelle Klauseln auf),
*setQuery* (stelle eine Anfrage) und *addObject* (füge Objekt hinzu). 

Die allgemeinste Beschreibung dieses Restriktionssystems ist, dass der Programmierer eine Serie
von Prolog-Klauseln definiert (Fakten und Regeln), welche unter Nutzung der definierten Prolog-Anfrage,
für jedes hinzugefügte Objekt angefragt werden. Dies wird für jemanden, der dies zum ersten Mal liest 
keinen Sinn ergeben. Ein Beispiel sollte die Konzepte und den Prozess etwas klarer machen:

```
setClauses("bewege(roboter, norden, X, R) :- X = noerdlicherWall, R = falsch.")

setQuery("bewege(roboter, %s, %s, R).")
```

In diesem Beispiel wird nur eine Regel definiert. Die Regel kann grob als "wenn der Roboter sich
nach Norden bewegen möchte, frage was X ist. Wenn X die nördliche Wand ist (northWall), dann kann
er sich nicht bewegen" übersetzt werden. Die Anfrage ist nur ein Stringformat, das als Anfrage für 
die *move*-Aktion (Bewege) und für das *robot*-Element (Roboter) dient, welches zwei weitere 
Argumente erhalten wird: Die Richtung und ein Objekt.

Objekte können mittels der *addObject*-Funktion definiert werden:

```
addObject("suedlicherWall")
addObject("noerdlicherWall")
```

Das Restriktionssystem wird das System für jedes dieser, im Modul präsenten, Objekte anfragen. 
In diesem Beispiel wird das System zuerst die Anfrage "bewege(roboter, norden, suedlicherWall)" ausführen und das System 
wird mit "nil" antworten, was bedeutet, dass es keine definierte Regel für diese Situation implementiert hat 
und die Standardaktion ist die Affordanz nicht zu verwerfen.
Die zweite Anfrage wird "bewege(roboter, norden, noerdlicherWall)" sein und das System wird mit "falsch" antworten.
In diesem Fall hat die Affordanz den Test nicht bestanden und wird verworfen.

Das obige Beispiel illustriert wie diese Regeln eine Affordanz unter der Benutzung einer Bedingung 
zunichte machen können. Regeln können jedoch auch für das Akzeptieren von Affordanzen verwendet werden,
selbst wenn diese von den vorherigen Regeln verneint wurden.

```
setClauses("bewege(roboter, norden, X, R) :- X = noerdlicherWall, R = falsch.
    bewege(roboter, norden, X, R) :- X = noerdlichesWurmloch, R = wahr.")

setQuery("bewege(roboter, %s, %s, R).")
```

Die hinzugefügte Regel im Code sagt dem System, dass es in Ordnung ist die nördliche Bewegung des 
Roboters zu akzeptieren, wenn ein Wurmloch vorhanden ist. Wenn das Objekt-Array unberührt bleibt, 
wird die Bewegungs-Affordanz trotzdem verworfen, aber wenn ein `"addObjekt("noerdlichesWurmloch")` 
ausgewerdet wurde, wird das "noerdlicheWurmloch" hinzugefügt und der Roboter kann nun durch die Wand
unter Verwendung des Wurmlochs durchlaufen.

# Striktes Typisierungssystem

Wie in der Einführung erwähnt gibt es kein implizites Casting in CX. Deshalb gibt es mehrere 
definierte Versionen der primitiven Typen im Kernmodul. Zum Beispiel gibt es vier native Funktionen
für die Addition: addI32, addI64, addF32 und addF64. 

Der Parser fügt einen Standarddatentyp zu den Daten, die er im Quellcode findet, hinzu:
Wenn ein Integer gelesen wird, ist der Standardtyp *i32* oder 32-Bit Integer; wenn ein Float
gelesen wird, ist der Standardtyp *f32* oder 32-Bit float. Es gibt keine Mehrdeutigkeit mit den
anderen, vom Parser gelesen, Daten: *true* und *false* sind immer Booleans; eine Serie von Symbolen
zwischen zwei doppelten Anführungszeichen sind immer Strings; einem Array muss seinem Typ vor der Liste
der Elemente angegeben werden, z.B., `[]i64{1, 2, 3}`.

Für die Fälle, in denen der Programmierer explizit einen Wert in den Typ eines anderen casten muss, 
stellt das Kernmodul eine Anzahl von Casting-Funktion bereit, um mit primitiven Typen umzugehen. 
Zum Beispiel, `byteAToStr` castet ein Byte-Array zu einem String und `i32ToF32` castet einen
32-Bit Integer zu einem 32-Bit Float.

# Kompiliert und Interpretiert

Die CX-Spezifikation schreibt einen CX-Dialekt vor, um dem Entwickler zugleich einen Interpreter und einen
Compiler bereitzustellen. Ein interpretiertes Programm ist, wie zu erwarten, wesentlich langsamer als sein kompiliertes 
Gegenstück, aber erlaubt ein flexibleres Programm. Diese Flexibilität kommt von den Meta-Programmier-Funktionen und
Affordanzen, welche die Programmstruktur während der Laufzeit beeinflussen können.

A compiled program needs a more rigid structure than an interpreted
program, as many of the optimizations leverage this rigidity. As a
consequence, the affordance system and any function that operates over
the program's structure will be limited in functionality in a compiled
program.

The compiler should be used when performance is the biggest concern,
while a program should remain being interpreted when the programmer
requires all the flexibility provided by the CX features. In the
following subsections, some of these features are presented, without
the aim of serving as a tutorial, but rather as a mere introduction.

### Read-Eval-Print Loop

The read-eval-print loop (REPL) is an interactive tool where a
programmer can input new program elements and evaluate them. Starting
a new REPL session will print the following messages to the console:

```
CX REPL
More information about CX is available at https://github.com/skycoin/cx

*
```

The "*" tells the programmer that the REPL is ready to receive a new
line of code. The REPL will keep reading input from the user until a
semicolon and a new line character are encountered.

If no program was initially loaded into the REPL, CX will start with
an empty program. This can be seen if the `:dProgram true;`
meta-programming command is given as input:


```
* :dProgram true;
Program

*
```

The REPL is only printing the word "Program" followed by an empty
line. As a first step, a new module and function can be declared:

As the first steps, a new *main* module and a new *main* function
should be declared:

```
* package main;
Program
0.- Module: main

* func main () () {};
Program
0.- Module: main
	Functions
		0.- Function: main () ()

*
```

As can be seen, the program structure is being printed every time a
new element is added to the program.

### Meta-programming Commands

`:dProgram` was used in the subsection above. Any statement that
starts with a colon (:) is part of a category of instructions known as
"meta-programming commands."

Declaring elements in the REPL instructs CX to add them to the
program's structure. But, as in many other programming languages,
these declarations are limited to only be added, and at most be
redefined.

But, as in many other programming languages that provide a REPL, the
programmer is limited to adding new elements to a program and, at
most, redefining elements. Meta-programming commands allow the
programmer to be in more control on how the program's structure is
being modified.

`:dProgram`, `:dState`, and `:dStack` are used for
debugging purposes only, by printing the program's structure, the
current call's state, and the full call stack to the user,
respectively. `:step` instructs the interpreter to go forward or
backward in its execution. `:package`, `:func`, and `:struct`, known
as *selectors*, are used to change the program's scope. `:rem` gives
the programmer access to *removers*, which can be used to selectively
remove elements from a program's structure. `:aff` is used to access
CX's affordance system; this meta-programming command is used to both
query and apply affordances for the different elements of a
program. Lastly, `:clauses` is used to set a module's clauses to be used by the
[user-defined restrictions system](#user-defined-restrictions);
`:object` and `:objects` are used for adding and printing objects,
respectively; and the last two meta-programming commands: `:query`,
which is used for setting the module's query, and `:dQuery` which is a
helper for debugging the user-defined restrictions.

### Stepping

A program started in REPL mode can be initialized with a program
structure defined in a source file. For example:
current directory

```
$ ./cx --load examples/looping.cx

```

loads `looping.cx` from the examples directory (the full list of
examples can be found in the
[project's repository](https://github.com/skycoin/cx)). Even though a
program has been loaded, it has not yet been executed. In the REPL, in
order to execute a program one has to use the meta-programming command
`:step`. To run a program until the end, `:step 0;` must be used. But
`:step` is interesting because it can take other integers as its
argument (even negative integers). For example:

```
CX REPL
More information about CX is available at https://github.com/skycoin/cx

* :dStack false;

* :step 5;
0

* :step 5;
1

* :step 5;
2

*
```

The *examples/looping.cx* program is being run 5 steps at a time. We
can see that 5 steps are required in order for the program to
re-evaluate the *while* condition, print the counter, and add 1 to the
counter.

Likewise, we should "go back in time" if the REPL is instructed to
`:step -5`.

```
...

* :step 5;
2

* :step -5;

* :step 5;
2

*
```

After instructing CX to advance 5 steps again, the 2 is printed again
to the console. It must be noted that the counter is not just being
assigned with a different value. What is happening is that the call
stack is being reverted to a previous state.

### Interactive Debugging

A CX program will enter the REPL mode once an error has been
found. This behaviour gives the programmer the opportunity to debug
the program before attempting to resume its execution.

In the example below, a division by 0 error is raised, the REPL alerts
the programmer about the error, the last call in the call stack is
dumped, and the REPL continues its execution.


```
CX REPL
More information about CX is available at https://github.com/skycoin/cx

* package main;

* func main () () {};

* :func main;
main
:func main {...
	* foo := divI32(5, 3);
main
:func main {...
	* bar := divI32(10, 0);
main
:func main {...
	* :step 0;
fn:main ln:0, 	locals:
>> 1
fn:main ln:1, 	locals: foo: 1

Call's State:
foo:		1

divI32() Arguments:
0: 10
1: 0

0: divI32: Division by 0
main
:func main {...
	*
```

Likewise, if a program is given as input to the CX interpreter,
without calling the REPL, but an error is raised, the REPL will be
called for the programmer or system administrator to debug the
program:

```
$ ./cx examples/program-halt.cx
1

Call's State:
nonAssign_0:		1
nonAssign_1:		1

divI32() Arguments:
0: 5
1: 0

5: divI32: Division by 0
CX REPL
More information about CX is available at https://github.com/skycoin/cx

*
```

# Integrated Evolutionary Algorithm

The affordance system and meta-programming functions in CX allow the
flexibility of changing the program's structure in a supervised
manner. However, affordances can still be automated by having a
function that selects the index of the affordance to be applied.

`evolve` is a native function that constructs user-defined functions
by using random affordances. An iterative process is used to test

`evolve` follows the principles of evolutionary computation. In
particular, evolve performs a technique called genetic
programming. Genetic programming tries to find a combination of
operators and arguments that will solve a problem. For example, you
could instruct `evolve` to find a combination of operators that, when
sent 10 as an argument, returns 20. This might sound trivial, but
genetic programming and other evolutionary algorithms can solve very
complicated problems.

In the *examples* directory from the repository, one can find an
example (*examples/evolving-a-function.cx*) that describes the process for
evolving a
[curve-fitting](https://en.wikipedia.org/wiki/Curve_fitting) function.

# Serialization

A program in CX can be partially or fully serialized to a byte
array. This serialization capability allows a program to create a
program image (similar to
[system images](#https://en.wikipedia.org/wiki/System_image)), where
the exact state at which the program was serialized is
maintained. This means that a serialized program can be deserialized,
and resume its execution later on. Serialiation can also be used to
create backups.

A CX program can leverage its integrated features to create some
interesting scenarios. For example, a program can be serialized to
create a backup of itself, and start an
[evolutionary algorithm](#integrated-evolutionary-algorithm) on one of
its functions. If the evolutionary algorithm finds a function that
performs better than the previous definition, one can keep this new
version of the program. However, if the evolutionary algorithm
performed badly, the program can be restored to the saved backup. All
of these tasks can be automated.

