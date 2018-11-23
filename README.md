# Programming Concepts & Paradigms

 <i style=float:right;>Luca Dias</i> <br>

## Notes SW 1.1

___
<i style=float:right;>Donnerstag, 20. Sep</i>

![Programmierparadigmen](img/programmierparadigmen.JPG "Programmierparadigmen")

Typisch für imperative Paradigmen:  

* man gibt sequenzielle Anweisungen (imperativ -> befehlen)  
* es gibt verschiedene kontrollflussstrukturen

### Kontrollfragen 1

1. Charakterisieren Sie in eigenen Worten, wie imperative Programmierung funktioniert. Aus welchen Grundelementen sind imperative Programme aufgebaut? Wie werden derartige Programme ausgeführt, wie verläuft der Kontrollfluss?
    * Der Code gibt an was der Computer in welcher Reihenfolge tun soll
    * Es gibt 3 Kontrollflussdingens (Sequenz, Schleifen, Verzweigungen)
2. In welchem Verhältnis stehen imperative und strukturierte Programmierung?
    * Eine Strukturierte Sprache ist eine spezialisierung der imperativen Sprachen
3. Durch was hebt sich die prozedurale Programmierung vom imperativen Programmierparadigma ab?
    * Prozedurale Programmiersprachen besitzten Prozeduren (oder auch als Funktionen/Methoden bekannt)
    * Es können Argumente übergeben werden und die kann Resultate zurückliefern
    * Lokale und Globale Variablen

## Notes SW 1.2

___
 <i style=float:right;>Freitag, 21. Sep</i>

### Kontrollfragen 2

1. Was ist ein ADT
    * ADTs sind abstrakte Datentypen, sie bestehen aus Datenstrukturen und definierten Operationen (z.B. ein Stack)
2. Worin unterscheidet sich die Implementierung von einem ADT in C fundamental von einer Implementierung in Java?
    * Im C: Bei der Implementierung der Datenstruktur sind die dazugehörige Funktionen sind "getrennt" implementiert
    * Java: Sind in einer Klasse "zusammen"
3. Um welche Konzepte erweitert die OOProgrammiersprache Java im wesentlichen die prozedurale Programmiersprache C?
    * Klassen und Instanzen (class, new, this, super)
    * Zugriffsmodifizierer (Public, Protected, Private)
    * Exception-Handling


## Notes SW 2.1

___
 <i style=float:right;>Donnerstag, 27. Sep</i>

### Prolog

PROgrammation en LOGique


#### Funktionsweise von Prolog

Wissensdatenbank:

* Bestehend aus Fakten & Regeln
* Kann abgefragt werden durch Anfragen (Queries)

![Programmierparadigmen](img/prologwissensdatenbank.JPG "Programmierparadigmen")


1. Wie antwortet das Prolog-System in unserem Beispiel auf die Anfrage is_bigger(elephant, fly)?
    * false
2. Was ist in unserem Beispiel der Unterschied zwischen bigger(X, Y) und is_bigger(X, Y)?
    * is_bigger(X,Y) ist transitiv
3. Definieren sie für das gegebene Beispiel eine Regel für is_smaller(X, Y).  (Hinweis: Das geht in einer Zeile)
  
```prolog
   * is_smaller(X,Y):- is_bigger(Y,X)
```

## Notes SW 2.2

___
 <i style=float:right;>Donnerstag, 27. Sep</i>

### Prolog


1. Wie viele Lösungen für das angegebene
Kreuzworträtsel findet unser Programm
grundsätzlich?
    * eine lösung, alle möglichen lösungen
2. Unser Programm findet für das angegebene
Kreuzworträtsel genau eine Lösung. Wie liesse sich
das Kreuzworträtsel einfach erweitern, so dass es
neu eine zweite Lösung findet? Wie müssten wir
dazu das angegeben Programm erweitern?
(Machen sie konkrete Vorschläge!)
    * weitere wörter hinzufügen
    * bsp asdfasdf, ran
3. Was würde Prolog antworten, wenn es für ein
angegebenes Kreuzworträtsel gar keine Lösung
gibt?
    * false


1. Wie können sie mit dem angegebenen Prädikat fak/2 herausfinden, was das X bei X! = 720 ist?
    *ausprobieren
2. Wie können sie mittels fib/2 überprüfen, ob die 8te Fibonacci-Zahl 21 ist?
    * fib(8,21). gibt true aus
3. Was würde passieren, wenn sie beim angegebenen Prädikat fib/2 die beiden Zeilen „N1 = ...“ und „N2 = ...“ weglassen und stattdessen die beiden rekursiven Aufrufe direkt machen als fib(N-1, F1) und fib(N-2, F2)? Funktioniert die Berechnung trotzdem? Begründen sie ihre Antwort.
    * geht nicht da keine operation

## Notes SW 3.1

___
 <i style=float:right;>Donnerstag, 4. Okt</i>

### Prolog

1. Warum kann eine endrekursive Prozedur von
Prolog effizienter ausgeführt werden, als eine
nicht-endrekursive Prozedur?
    * bereits berechnete werte wiederverwendet
2. Beschreiben sie in eigenen Worten, auf was für
einer Beobachtung „Optimierung mit Assertions“
beruht und wie diese konkret in Prolog umgesetzt
wird.
    * caching
    * 


1. Was antwortet Prolog auf die folgende Anfrage:
    X = [a | [b]]?
    *   X = [a, b].
2. Was antwortet Prolog auf die folgende Anfrage:
[1, 2, 3] = [_ | X]?
    * X = [2, 3].
3. Und was auf diese: [a, b, c] = [_, X | Y]?
    * X = b,
    * Y = [c].

4. Warum ist es in Prolog i.A. effizienter auf das erste,
als auf das letzte Element einer Liste zuzugreifen?
    * erstes linkes element der baums
    *   

1. Was antwortet Prolog auf die folgende Anfrage:
conc(L, [c], [a, b, c])?
    * L = [a, b]

2. Was antwortet Prolog auf die Anfrage
conc(Before, [d | After], [a, b, c, d,e, f, g, h]).?
    * Before = [a, b, c],
    * After = [e, f, g, h] 

3. Und was auf conc([a], L, [b, c])?
    * false

4. Bonusaufgabe (schwierig): Wie lässt sich mem/2 unter Verwendung von conc/3 ausdrücken? (D.h.als neues Prädikat der Form mem_c(X, L) :- ...conc...)
    * mem_c(X, L) :- conc(_, [X | _], L).

## Notes SW 4.1

___
 <i style=float:right;>Donnerstag, 11. Okt</i>

### Kontrollfragen


1. Was antwortet das Programm mit Mary und den
Schlangen auf die Anfrage likes(mary, cat)?
Begründen Sie ihre Antwort.  
    * false  
    * Prolog weis nicht das eine Katze ein Tier ist wegen der CWA (Closed word assumption).

2. Was antwortet dasselbe Programm auf die Anfrage
likes(X, dog)?  
    * X = mary.
3. Wie lässt sich mit Hilfe vom Cut und dem fail/0-
Prädikat in Prolog ein not/1-Prädikat aufbauen?
    * prädikat, !, fail
    * 2te regel mit true

4. Wie heisst das zu not/1 äquivalente eingebaute
Prolog-Prädikat?
    * \\+

5. Auf was sollten wir beim Einsatz von not/1 in Bezug
auf die zu negierenden Ziele achten?
    * in diesen Zielen sollten kein nicht instanziierten variablen vorkommen


1. fib_clp/2 sei programmiert wie vorhin besprochen.
Was ist die Antwort von Prolog auf die Anfrage
fib_clp(N, F)?

    * N = F, F = 0.0 ;  
N = F, F = 1.0 ;  
N = 2.0,  F = 1.0 ;  
N = 3.0,  F = 2.0 ;  
N = 4.0,  F = 3.0 ;  
N = F, F = 5.0 ;  
N = 6.0,  F = 8.0 ;  
N = 7.0,  F = 13.0 ;  
N = 8.0,  F = 21.0 ;  
N = 9.0,  F = 34.0  



2. Was antwortet Prolog (im CLP-R-Modus) auf die
Anfrage { X =< 4, X >= 3 + 1 }?

    * X = 4.0.

3. Und was auf { X + 1 >= 2 }?
    * {X>=1.0}.

4. Und was im CLP-FD-Modus auf die Anfrage
X in 1..2, X #> 2?
    * false

5. Und was auf [X, Y] ins 1..2,
all_distinct([X, Y]), X #= 1?
    * X = 1,
Y = 2.


## Notes SW 4.2

___
 <i style=float:right;>Freitag, 12. Okt</i>

### Kontrollfragen

Wan ist ein proglem ist ein CLD Problem
-> ein definierter wertebereich z.B. bei sudoku 1 bis 9
-> variablem z.b. bei sudoku die zahlenfeldert
-> constraints z.b. bei sudoku jede zahl nur 1mal in einer reihe/spalte vorkommen kann


1. Was bewirkt das eingebaute Prädikat all_distinct/1 ? 

    * alle variablen müssen sich unterschseiden
    ```prolog
    all_distinct([1,2,3,4]).
    true.
    ``` 
  

2. Was bewirkt das eingebaute Prädikat maplist/2 ? Erläutern Sie die Anwendung an einem eigenen Beispiel.

    * ein prädikat wird auf die liste angewendet, z.b. all_disctinct auf die list "rows"
    ```prolog 
    maplist(all_distinct,[[1,2,3,4],[1,2]]).
    true.
    ```
    

3. Was bewirkt transpose/2 auf eine Liste von Listen? Machen Sie zur Illustration ein Beispiel dazu.

    * transponiert die liste vom ersten parameter in den 2ten, trasnponieren ist das vertauschen von spalten in zeilen
    ```prolog 
    transpose([[1,2],[3,4]],X).
    X = [[1, 3], [2, 4]].
    ```

4. Was passiert, wenn sudoku/1 mit einer Liste von 9 Listen mit je 9 anonymen Variablen aufgerufen wird? (Was ist also die von Prolog ermittelte Lösung zu einer
Sudoku-Instanz ohne vorgegebene Zahlen?)

    ```prolog
    A = [1, 2, 3, 4, 5, 6, 7, 8, 9],  
    B = [4, 5, 6, 7, 8, 9, 1, 2, 3],  
    C = [7, 8, 9, 1, 2, 3, 4, 5, 6],  
    D = [2, 1, 4, 3, 6, 5, 8, 9, 7],  
    E = [3, 6, 5, 8, 9, 7, 2, 1, 4],  
    F = [8, 9, 7, 2, 1, 4, 3, 6, 5],  
    G = [5, 3, 1, 6, 4, 2, 9, 7, 8],  
    H = [6, 4, 2, 9, 7, 8, 5, 3, 1],  
    I = [9, 7, 8, 5, 3, 1, 6, 4, 2]  
    ```

#### Was bedeuten die + und - bei den Prädikaten?
```prolog
http_get(+URL,-Reply,+Options).
```
![Plus Minus](img/plusminus.JPG "Plus minus")

1. Thema HTTP: mit welchen beiden Prädikaten werden aus Prolog GET- resp. POST-Anfragen gestellt?

    ```prolog
    http_get('http://wherever.ch/pcp.txt', Reply, []).

    http_post('http://localhost:16316/test',json(['say hi to http post']),SolutionResponse,[]).
    ```

2. Was erwarten sie für eine Antwort bei einer GETAnfrage auf die nicht-existente URL „http://www.invalid-url.net/“?

    * ERROR: Socket error: Host not found

3. Aus welchen Elementen sind JSON-Objekte grundsätzlich aufgebaut? Machen sie je ein Beispiel für jeden Element-Typ.

    * Objekte = Menge von Schlüssel/Werte-Paaren, in { }
    * Arrays = Sequenz von JSON-Objekten, in []
    * Werten (Strings, Zahlen,Boolean, null)

4. Was können Sie mit dem eingebauten Prädikat call/2 tun? Illustrieren Sie an einem Beispiel.

    * Ich kan ein Beliebiges Prädikat mittels dem call/2 wie folgt aufrufen.

    ```prolog
    ?- call(is_bigger, horse, dog). 
    true .
    ?- call(is_bigger, horse, X). 
    X = dog
    X = sheep
    ```

5. Wie kann maplist/3 eingesetzt werden? (inkl. Beispiel)

    * Funktioniert wie maplist/2 aber das Ergebnis wird im dritten parameter gespeichert
    ```prolog
    ?- maplist(sqrt, [4, 9, 16], X). 
    X = [2.0, 3.0, 4.0].
    ```


## Notes SW 5.1

___
 <i style=float:right;>Donnerstag, 18. Okt</i>

### Scheme

Einleitung zeugs


### Kontrollfragen

1. Was ergibt (- 20 5 2) und (/ 20 5 2)?
    ```scheme
    > (- 20 5 2) 
    13
    > (/ 20 5 2)
    2
    ```


Was ist falsch an den folgenden Ausdrücken?  
* (5 * 14)
    * zuerst * dann beide operanden
* (* (5) 3)
    * klammer zu viel
    
* (+ (* 2 4)
    * das + hat nut einen summand

* (* + 3 5 2)
    * zwei operanden zur gleichen zeit

* (/ 25 0)
    * division durch 0


1. Scheme ist dynamisch typisiert. Was bedeutet das?
    * Man definiert die Typen der Variablen nicht selber.
2. Wie wird der folgende Ausdruck schrittweise ausgewertet?
(* (- 6 4) (+ 3 2))
    * zuerst werden die 2 inneren werte ausgewertet

3. Wie sehen die Auswertungsregeln für allgemeine Formen
aus?
    * Rekursiv
    * zuerst innere terme, sonsten von links nach rechts

![Auswertung Scheme](img/auswertungscheme.png "Auswertung Scheme")

4. Wie sieht die Auswertungsregeln für die spezielle Form
define aus?  
    * ( define ( g x y) ( + x y))


## Notes SW 5.2

___
 <i style=float:right;>Freitag, 19. Okt</i>

### Scheme 2

```scheme
>(< 3 1)
false
> (<= 5 5)
true
>(<= 3 4 5 5) ;Bedingung stimmt da 5 grösser gleich 5 ist
true
> (< 3 4 5 5) ;Bedingungen stimmt ncht das 5 nicht grösser als 5 ist
false
> (and (= 23.3 23.3) (< 5 7)) ; Boolsches and
true
> (and true (+ 3 5))
and: question result is not true or false: 8
```

### Kontrollfragen

1. Was sind elementare Prädikate?
    * selbsauswertende Werte
2. Welche elementare Prädikate kennen Sie?
    * true oder false
3. Wie werden boolesche Verknüpfungen (and, or)
ausgewertet?
    * von links nach rechts, lazy evaluation, kurzschlussverfahren z.B. bei OR wird beim ersten true ausdruck direkt true zurückgegebn
4. Was sind Prädikatfunktionen?
    * Testen eine Bedingung und geben true oder false zurück
5. Woran erkennt man Prädikatfunktionen?
    * am fragezeichen -> even?
6. Welche Arten von Prädikatfunktionen kennen Sie?
    * Tests auf Zahlen, Basistypen und Gleicheit

### Symbol

Bis jetzt hatten wir Zahlen und Booleans als elementare
Werte kennengelernt.
Oft wollen wir symbolische Informationen speichern:  
* Namen, Wörter, Richtungen,…  

Ein Symbol ist in Scheme eine Sequenz von Zeichen,
angeführt von einem einfachen __Anführungszeichen__:

* 'the 'dog 'ate 'a 'cat! 'two^3 'and%so%on?

* Nicht alle Zeichen sind erlaubt (z.B. keine Leerzeichen)  

Nur eine Operation auf diesem Datentyp: __symbol=?__  
Symbole sind atomar (wie auch Zahlen, Booleans).  
Symbole können nicht zerlegt werden.

Ob Objekte gleiche (Gleichheit) Symbole sind, kann mit der
Prädikatfunktion __symbol=?__ getestet werden.

```scheme
> (symbol=? 'Hallo 'Hallo)
true
> (symbol=? 'Hallo 'ABC)
false
> (symbol=? 1 2)
symbol=?: expects a symbol as 1st argument, given 1
>
```


### Kontrollfragen 2
1. Wie wird cond-Anweisung ausgewertet?  
    * Die Bedingungen werden der Reihe nach überprüft, beim ersten true wirds ausgewertet
2. Was passiert, wenn keine Bedingungen der cond-Anweisung
zutrifft?
    * gibt ein fehler
3. Was ist das besondere an der if-Anweisung, gegenüber
anderen Programmiersprachen (z.B. Java)?
    * es braucht ein else teil sonst gibt es ein fehler.


### Kontrollfragen 3

1. Welche impliziten Funktionen gibt es zu der 
_define-struct_ Anweisung?
    * prädikatsfunktion, selektor - , Kontstruktor : make
2. Wie wird ein Objekt einer define-struct erzeugt?
    * (define p1 (make-point 3 4))
3. Wie werden die Datentypen der Felder festgelegt?
    * gar nicht, sie werden dynamisch typisiert.
4. Erweitern Sie die Point Scaling Funktion mit dem Check auf
die korrekten Datentypen. Fehlermeldung kann mit error
ausgegeben werden.  
    * integer?


## Notes SW 6.1

___
 <i style=float:right;>Donnerstag, 26. Okt</i>

### Scheme 3


### Kontrollfragen 1

1. Beschreiben Sie was eine Liste ist.
    * ein container mit mehreren variablen
    * eine verkettung von elementen
    * rekursiv definierte datentypen
    * empty
2. Welche Art von Elementen (Datentypen) kann eine Liste
enthalten?
    * alles -> ints, bools, symbols, listen
3. Mit welchen Funktionen können Sie eine Liste erstellen
(konstruieren)?
    * mit cons oder mit list   
4. Mit welchen vordefinierten Funktionen können Sie auf
Elemente einer Liste zugreifen?
    * mit first oder mit rest
5. Was erhalten Sie als Ausgabe mit folgender Anweisung?
(rest (rest (list 1 2 3 4))  
    * (list 3 4)
6. Wie greifen Sie auf das zweite Element einer Liste zu?  
    * (first (rest (list 1 2 3 4)))

### Kontrollfragen 2

1. Wie sieht das Funktionsschema für Operationen auf Listen
aus?  
__mache-etwas-mit Liste__  
    * ist leer: Spezialfall  
    oder  
    *  behandle erstes Element  
    * __mache-etwas-mit__ dem Rest der Liste

2. Bei welchen Listen oder Operationen auf Listen kann man
das Funktionsschema nicht anwenden?
    * leer, redouble

3. Was bedeutet wohldefinierte Rekursion?
    * Die Auswertung der Funktion terminiert.
    * keine endlos loops

4. Schreiben Sie eine Rekursion, die nicht wohldefiniert ist?  
    * 


## Notes SW 6.2

___
 <i style=float:right;>Freitag, 26. Okt</i>

### Scheme 4

```scheme
; Finde das Maximum in einer Liste von Zahlen
(define (list-max a-list)
  (list-max-helper (rest a-list) (first a-list)))

; Hilfsfunktion für das Finden das Maximum in einer Liste von Zahlen
(define (list-max-helper a-list max-so-far)
  (cond
    [(empty? a-list) max-so-far] ; wenn liste leer -> max-so-far ist grösstes element
    [(> (first a-list) max-so-far) ; ist erstes element grösser als max-so-far -> neues max-so-far
     (list-max-helper (rest a-list) (first a-list))]
    [else
     (list-max-helper (rest a-list) max-so-far)]))

; Demo
(list-max (list 1 2 3 4))
;(list-max (list 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25))
```


### Kontrollfragen 1

1. Welche Randbedingung muss erfüllt sein, damit Sie eine strukturelle Rekursion einsetzten können?
    * man kann schrittweise zum basisfall kommen
    * bei einem erneuten Aufruf sind Parameter entweder unverändert oder eine Stufe näher zum Basisfall.
    * Die Daten müssen ein rekursive struktur haben, rekursiver Aufbau (oder auch: Induktive Daten).
2. Was ist der Vorteil einer akkumulativen Rekursion gegenüber einer normalen strukturellen Rekursion?
    * Sie merkt sich ein Wert (z.B. max-so-far)
    * Bessere Performance
        * es gibt weniger aufrufe und ich brauche weniger Stack
3. Wann spricht man von einer generativen Rekursion?  
    * Wenn nicht nichts "mechanisch" abgearbeitet wird. -> also nicht schrittweise zum basisfall
4. Was ist bei einer generativen Rekursion besonders zu beachten?  
    * parameter werden bei jedem Aufruf neu berechnet.
    * auf terminierung der Rekursion achten.
5. Nach welchem Prinzip gehen Sie beim Entwurf einer generativen Rekursion vor?  
     * Man teilt das Problem in kleinere Probleme auf und versucht diesee zu lösen und danach wieder zu kombinieren
    * __teile und herrsche__

### Kotrollfragen 2

1. Nennen Sie den Unterschied zwischen Funktionen erster Ordnung und Funktionen höherer Ordnung.
    * Funtkionen höherer Ordnung können selber Funktionen als Parameter oder Resultate haben.
2. Wann werden Funktionen in einer Programmiersprache als «Werte erster Klasse» behandelt?
    * wenn sie als Parameter an andere Funktionen übergeben werden können,
    * Wenn sie  als Resultate von Funktionen zurückgegeben werden können
    * wenn sie zur Laufzeit erzeugt werden,
3. «Higher-Order Functions» verbessern die Expressivität einer Programmiersprache. Was bedeutet dies?
    * die Fähigkeit komplexe sachverhalte möglichst klar und einfach auszudrücken.
    * code wird lesbarer
4. Wenn Sie eine eigene Funktion/Operator für die vordefinierte Funktion filter schreiben, auf welche Randbedingungen müssen Sie achten?
    * _filter_ wendet _\<function>_ auf jedes Element von _\<list>_ an und filter liefert eine neue Liste von Elementen zurück, auf die _\<function>_ zutrifft.
    * _\<function>_ darf nur ein Argument besitzen.
    * _\<function>_ muss einen booleschen Wert zurückliefern.
    ```scheme
    (filter <function> <list>)
    ```


## Notes SW 7.1

___
 <i style=float:right;>Freitag, 2. Nov</i>


__Wichtig Lambda teil der Endprüfung__

### Scheme 5

#### Kontrollfragen 1

1. Wann besteht Bedarf lokale Definitionen anzuwenden? 
    * bei akkumulativen Rekursionen sind zum Beispiel Hilffunktionen wertvoll welcher nur in dem Scope definiert sein müssen
    * alle nameaufgebraucht hat, oder bei vielen funktionen
    * namenskonflikte aus dem weg gehen
2. Wie viele Definitionen sind innerhalb einem lokal-Block möglich?
    * beliebig viele , zu viele locals
3. Was bedeutet lexikalisches Scoping?
    *
4. Welche Bereiche bei der Namensbindung sind Ihnen in Scheme bekannt?
    *  3 bereiche
    * top level
    * funktion mit dem funktionsparameter
    * local definition, lokale definition innerhalb einer funktion


#### Kontrollfragen 2
1. Die Auswertung eines λ-Ausdrucks liefert eine Funktion mit entsprechender Parameterzahl. Was heisst das?
    * das gleiche mit einer vordefinierten Funktion die einen namen hat,

2. Wann ist der Einsatz eines λ-Ausdrucks sinnvoll?
    * macht nur sinn wenn ich sie nur 1 mal brauche, oder ich sie nur lokal definieren muss
    * 1mal wiederverwendebar

3. Weshalb können anonyme Funktionen nicht rekursiv sein?
    * weil sie anonym sind



## Notes SW 7.2

___
 <i style=float:right;>Freitag, 2. Nov</i>


### Scheme 6

Wichtige Eigenschaften von Funktionen 
* Egal, wie oft wir eine Funktion mit ein und derselben Eingabe benutzen, wir bekommen immer das gleiche Ergebnis
* An jeder Stelle eines Programms können wir einen Funktionsaufruf durch seine Definition oder seinen Wert ersetzen, ohne den Sinn des Programms zu verändern – Wir können (+ 3 5) durch 8 ersetzen 
    * Wir können (map succ (list 3 5)) durch ((lambda (f alist) ... ) succ (list 3 5)) ersetzen, wobei ... die Definition von map und succ eine Funktionsdefinition ist
    * Wir können (map succ (list 3 5)) durch (list 4 6) ersetzen, wenn succ die Definition von Parameter + 1 ist
* Diese Eigenschaft wird referentielle Transparenz genannt
* Dieser Programmierstil wird als rein funktional bezeichnet

#### Kontrollfragen 1

1. Kennen Sie einen Begriff, der das Verhalten einer «Funktion mit Gedächtnis» umschreibt?
    * Seiteneffekt
    * Nebeneffekt
2. Wie würden Sie die Zuweisung set! in der funktionalen Programmierung einordnen?
    * 
3. Wie wurde die Sequenz bisher, ohne die begin-Anweisung, in Scheme umgesetzt?
    * 
4. Was ist der Unterschied zwischen der Abarbeitung einerSequenz und der Abarbeitung aus der Antwort der Frage 3?
    * aufwertungsreihenfolge ist relewant



## Notes SW 8.1

___
 <i style=float:right;>Donnerstag, 8. Nov</i>


 ### Java

Worin unterscheiden sich abstrakte Klassen von Interfaces und Abstrakten klassen?


#### Kontrollfragen 1

1. Wie sieht ein Lambda-Ausdruck aus, welcher zwei float-Argumente nimmt, und den grösseren von den beiden Werten zurückliefert?
```java
(a,b) -> return (a > b) ? a : b
```
2. Wie sieht ein Lambda-Ausdrück aus, welcher ein Argumente vom Referenztyp Item nimmt, dann auf dieser Instanz die Methoden check() und setId(77) aufruft und nichts zurückliefert?
```java
(Item c) -> {c.check(); c.setId(77);}
```

#### Kontrollfragen 2

1. Geben Sie die Code-Zeile an, welche die InstanzMethode String toUpperCase() der Klasse String als Methoden-Referenz einer Variable x zuweist. Von welchem Typ eines funktionalen Interfaces aus java.util.function muss x deklariert werden?
```java
UnaryOperator<String> x = String::toUpperCase;
```

2. Dieselbe Aufgabe wie bei 1., dieses mal sollen sie jedoch die Instanz-Methode boolean isEmpty() der Klasse String einer Variablen y vom passenden Typ (= welchem?) zuweisen.
```java
Predicate<String> y = String::isEmpty;
```

3. Welcher Typ aus java.util.function passt für eine Referenz auf eine Methode, welche als Argumente zwei Strings nimmt und einen boolean–Wert zurückliefert?
```java
 BiPRedicate<String, String>
 ```

 #### Kontrollfragen 3

 1. Welchem funktionalen Interface aus java.util.function liesse sich rein formal der folgende Lambda-Ausdruck aus dem Listener-Beispiel von oben auch zuweisen? e -> System.out.println(“Detected by ...”)  
```java
Consumer<ActionEvent>
```

2. Wie können Sie mit Hilfe der gezeigten neuen Methode
Iterable.forEach(...) auf einer Collection<Account> auf
jeder Account-Instanz die Methode check() aufrufen?
Geben Sie die entsprechende Code-Sequenz an. 
```java
accounts.forEach(b -> b.check())
```

3. Was ist Typ und Wert von x im Code-Beispiel auf der vorangehenden Folie? (Hinweis: Streams und Aggregate-Operations behandeln wir nächstes mal! -
Sie können bei dieser Aufgabe also einfach raten oder
kreativ überlegen, was für ein Typ und Wert für x Sinn
machen könnte. :-)
```java
Optional<String>
```

## Notes SW 8.2

___
 <i style=float:right;>Freitag, 9. Nov</i>


#### Kontrollfragen A

1. Beschreiben Sie in eigenen Worten, zu welchem Zwecke in Java 8 Streams eingeführt wurden.
    * _"A sequence of elements supporting sequential and parallel aggregate operations."_
    * um darauf einfacher Lambdas anzuwenden
    * ermöglichen Aggregate Operations -> also Funktionen elegant auf Datenstrukturen anwenden.
2. Weisen Sie der Variablen IntStream is einen Stream mit dem Zahlenbereich von 10 bis 100 (inklusive) zu. Wie sieht der entsprechende Code aus? Hinweis: Verwenden Sie dazu die passende IntStream-Factory-Methode range(...).
    ```java
    IntStream is = IntStream.range(10,101);
    ```
3. Weisen sie der Variablen Stream<String> stringStream unter Verwendung der FactoryMethode Stream<T>.of(T... values) einen Stream mit den Strings "a", "b" und "c" zu.
    ```java
    Stream<String> stringStream = Stream.of("a","b","c");
    ```

#### Kontrollfragen B

1. Wie könnte die Methode IntStream.sum() unter Verwendung von IntStream.reduce(int identity, IntBinaryOperator op) und einer Methoden-Referenz implementiert werden?
    ```java
    IntStream is = IntStream.range(10,123);
    is.reduce(0, Int::sum)
    ```

2. Geben Sie eine Code-Sequenz an, welche für alle Ganzzahlen von 0 bis 10 die durch 3 teilbaren herausfiltert, zu diesen je 1 dazu zählt und diese Zahlen dann miteinander multipliziert. Das Resultat ist also 280 = 1 \* 4 \* 7 * 10 = (0+1) * (3+1) * (6+1) * (9+1). Hinweis: Verwenden Sie dazu u.a. die Stream-Operationen filter, map und reduce.
    ```java
    int sums = IntStream.range(0, 11).filter(i -> i%3==0).map(i -> i+1).reduce(1, (i1, i2) -> i1*i2);
    ```

#### Kontrollfragen C

1. Worin unterscheiden sich stateless und stateful Operationen? Welche sind performanter?
    * stateless -> braucht nur info vom objekt, operation hängt nur vom aktuellen objekt ab
    * statefull -> resultat hängt noch von etwas zusätlichem ab, z.b. andere Elemente

    * stateless sind performanter -> sind nicht abhängig vom zustand

2. Erläutern Sie an einem Beispiel, was Zustand bei stateful-Operations konkret bedeutet.
    * Operation braucht zusätzlichen Zustand und aktuelles Stream-Element um zu entscheiden was zu tun...
    * zu beispiel bei sorted muss es andere Elemente kennen damit er sie vergleichen kann
3. Erläutern Sie je ein konkretes Beispiel (d.h. eine Methode) für eine intermediate- und eine terminalOperation, die "short-circuiting" ist. Unter welchen Umständen kürzen die von ihnen gewählte Methoden die Berechnung ab?
    * _.limit()_ -> wenn limit erreicht wird geshort circuited
    * _.anyMatch()_ -> beim ersten true wird terminiert -> stream ist nun aufgebraucht und kann nicht mehr verwendet werden.

4. Wie lässt sich ein gegebener sequentieller Stream s von Strings in einen parallelen Stream p umwandeln?
     ```java
    long sampleSize = 1_000000;
        double sum = DoubleStream.generate(Math::random)
                                    .skip(7_000_000L)
                                    .parallel() //hier brudi
                                    .limit(sampleSize)
                                    .sum();
        System.out.println("average = " + (sum / sampleSize));
    ```


    
## Notes SW 9.1

___
 <i style=float:right;>Donnerstag, 15. Nov</i>

Kontrollfragen A

1. Nennen Sie möglichst viele in Java 8 eingeführte Aggregat-Operationen auf Streams. Beschreiben Sie dazu in eigenen Worten, wie die einzelnen Operationen funktionieren.
    * filter -> ein predikat wird auf die lsite angewendet
    * reduce -> terminal , not-short-circuit, filter elemente über ein prädikat
    * forEach ->
    * map
    * count -> zählt wie viele werte im stream sind
    * sum -> sum der weter im Stream
    * limit -> limitiert den stream
    * getAsInt -> holt den 
    * anyMatch -> schaut ob ein element meine expression matched (beim ersten gibt er true zurück) bzw boolean
2. Worin unterscheiden sich intermediate und terminal Stream-Operationen fundamental?
    * intermediate Stream werden erst ausgewertet wenn eine terminal-Operation ausgeführt wird -> lazy evaluation
    * terminal Stream Opeartionen verbrauchen den Stream, er kann danach nicht wieder verwendet werden. -> eager evaluation
3. Zu welchem Zweck wurde in Java 8 die Klasse Optional<T> eingeführt? Geben Sie ein Beispiel für einen sinnvollen Einsatz von dieser Klasse im Kontext von Streams.
    * verhindert Null-Pointer-Exceptions
    * A container object which may or may not contain a nonnull value. If a value is present, isPresent() will return true and get() will return the value. Additional methods that depend on the presence or
    absence of a contained value are provided, such as orElse() (return a default value if value not present) and ifPresent() (execute a block of code if the value is present). This is a value-based class; use of identity-sensitive operations (including reference equality (==), identity hash code, or synchronization) on instances of Optional may have unpredictable results and should be avoided.

#### Natural Order

Die object Klasse implementiert dies oder so, möglich das für prüfung wichtig

Java Comparable interface intuition. By default, a user defined class is not comparable. That is, its objects can't be compared. To make an object comparable, the class must implement the Comparable interface

#### Futures
Zum Einstieg zwei Fragen an Sie:
1. Was kann bei der Programmierung von lange andauernden Aufgaben auf dem MainThread problematisch bzw. schwierig sein?
    * wenn man ein GUI hat blockiert das bei nur 1nem Thread
2. Wie programmieren Sie in Java nebenläufig, sprich so dass Code (vermeintlich) parallel laufen kann?
    * threads und runnables

#### Kontrollfragen 2

1. Wie lässt sich aus einer List<String> list mit den Elementen x, X und x mit Hilfe der Methode String.join(...) der String x-|-X-|-x erzeugen?
    ```java
    List<String> liste = new LinkedList<>();
    liste.add("x");liste.add("X");liste.add("x");
    String desiredString = String.join("-|-", liste);
    ```
2. Wie ist in Java „natürliche Ordnung“ zwischen Objekten definiert?
    * Interface Comparable
    * Methode compareTo();
    *rückgavewert: -1,0,1

3. Wie lässt sich in Java 8 einfach ein in umgekehrtnatürlicher Ordnung ordnender Comparator erzeugen?
    * reverse

4. Erläutern Sie an einem konkreten Beispiel, wie Sie mitels CompletableFuture<T> relativ einfach und elegant Code auf einem Hintergrund-Thread ausführen lassen können.
    *

#### Kontrollfragen C
1. Beschreiben Sie die erwähnte Analogie zwischen Garbage Collectors und funktionaler Programmierung in eigenen Worten.
2. Durch was wird Zustand in imperativen Programmen typischerweise ausgedrückt?
    * instanzvaraiblem
3. Worin unterscheiden sich imperative und funktionale Programmierung in Bezug auf den Zustand der verarbeiteten Daten?
    * nur funktionale programmierung sind daten immutable, man kann sie nicht ändern
    * daten können und werden geändert
4. Durch welche Stream-Methoden werden in unserem Beispiel die drei Operationskategorien filter, transform und convert in Java 8 abgebildet?
    * filter -> reduce
    * tranfsorm ->  
    * convert

## Notes SW 9.2

___
 <i style=float:right;>Freitag, 16. Nov</i>

#### Kontrollfragen A


1. Worin unterscheiden sich imperative und deklarative Programmierung fundamental?
    * imverative -> wie wird ein problem gelöst, mit answeisungen
    * deklarativ -> was, was ist zu tun, im wesentlichen wird die berechnungslogik geschrieben

2. Erläutern Sie den Unterschied zwischen typischer imperativer und funktionaler Programmierung am Beispiel „Company Process“.
    * in der cleanNames methode funktional kann ich die liste ganz einfach mit filter/map/reduce (funktionen höherer Ordnung)
    * imperativ muss ich das selber durchiterieren, ganz üblich for
3. Funktionale Programmierung erlaubt Modellierung auf höherer Abstraktionsstufe. Um welche tieferen Details müssen sich ProgrammierInnen in Java 8 mit Streams nicht kümmern? Nennen Sie ein konkretes Beispiel.
    *  parallel

4. Welches sind typische Funktionen höherer Ordnung in Java 8? Warum sind das Funktionen höherer Ordnung?
    * filter, map, reduce, forEach
    * sie nehmen funktionen als argumente entgegen
    * oder sie liefer ein funktion zurück


#### Kontrollfragen B

1. Sehen Sie Analogien zwischen den beiden gesehenen Beispielen „Company Process“ und „Zahlenklassifizierung“? Begründen Sie Ihre Antwort.
    * funktionale -> function higher order
    * imperativ -> schleifen / if /zustand
2. Was ist eine „pure function“?
    * Produzieren keine (beobachtbaren) Seiteneffekte wie Zustandsänderungen, oder Ausgabe
    * Produzieren für dieselben Argumente immer exakt dasselbe Resultat (sind also unabhängig von Zustand oder I/O)
    * referenzielle transparenz
3. Was haben Collections und Streams gemäss Neal Ford mit kinetischer und potentieller Energie zu tun? Erläutern Sie die erwähnte Analogie.
    * Java Collections verhalten sich wie kinetische Energie: sie lösen Werte sofort auf
    * Streams verhalten sich mehr wie potentielle Energie, gespeichert für den späteren Verbrauch


#### Prüfugnsfrage

Was ist an prolog imperativ?
die reihenfolge der ziele der prädikate ist relevant
der cut operator

Was ist an Scheme imperativ
let* oder begin


Folie Seite 41 -> StringPredicate, liefert einen wahrheitswert zurück, nimmt 1 argument an




## Notes SW 10.1

___
 <i style=float:right;>Donnerstag, 22. Nov</i>

### Kontrollfragen 10.1 A

1. Was versteht man unter Syntax?
    * Ist der Code syntaktisch korrekt geschrieben (klammern, strichpunkte), aufbau
    * zeichen, tokens, usw. müssen mit den "gramatik" regeln übereinstimmen
2. Was versteht man unter Semantik?
    * typenprüfung, varaiblen korrekt definiert, unreachable code
    * bedeutung der einzelnen zeichen
    * Semantik -> Bedeutungslehre
3. Ein Compiler besitzt ein Frontend und ein Backend.
    * Was heisst das?
        Die Kompilierung wird in 2 teile aufgeteilt, in die Analyse und die Synthese
    * Was sind die Aufgaben des Frontend und des Backend?
        Frontend -> gibt meldungen, bzw Zwischenrschritte und Zwischenresultate aus
        Frontend -> Lexikalische Analyse, Syntaxanalyse, 
        Backend -> code optimierung und code-Erzeugung
4. Was macht ein Scanner?
    * Identifikation von Operatoren, Symbolen, Schlüsselwörtern
    * Zerlegt den Quellcode in seine Bestandteile
    * Erzeugt Tokens daraus
    * Kommentare und irrelevantes wird entfernt
    * Scannt den Code zeile für Zeile
5. Was macht ein Parser?
    * Erzeugt aus den Tokens ein Syntaxbaum
6. Was ist die Aufgabe der Synthesephase?
    * Zweiter teil der Kompilierung
    * Aus dem Syntaxbaum wird maschinenunabhängiger Zwischencode erzeugt
    * Optimiert und erzeugt diesen Code
    * Ein Interpreter würde bei diesem Zwischencode fertig sein, und dieser könnte nun in einer Virtuelen Maschine (JVM, webengine) laufen.
7. Welche Art von Compiler nehmen Sie, um Ihre alten PascalProgramme in Java-Programme umzuwandeln?
    * Transcompiler


### Kontrollfragen B (Selbststudium)

1. Experimentieren Sie mit dem Java Programm Adam Riese.
2. Zeichen Sie einen «Abstrakten Syntaxbaum» mit den Begriffen aus unserer Definition für den arithmetischen Ausdruck: (1+2)*3=
3. Versuchen Sie mit Hilfe des Debuggers und des «Abstrakten Syntaxbaumes» die Methoden Aufrufe nachzuvollziehen.
4. Erweitern Sie das Programm mit den Rechenoperationen Subtraktion und Division.
5. Experimentieren Sie mit dem Scheme Programm Adam Riese und bearbeiten Sie die Punkte 3 (mit Stepper) und 4.



## Notes SW 10.2

___
 <i style=float:right;>Freitag, 23. Nov</i>

### Kontrollfragen A

1. Wie lautet die Definition von Sprache?
    * Sprache ist die
        * Menge von Sätzen
        * die sich aus einer definierten Menge von Zeichen
        * unter Beachtung der Syntaxregeln bilden lassen
2. Was ist ein terminales Alphabet?
    * Die Menge der Zeichen, aus denen die Sätze der Sprache gebildet werden
        ```java
        //terminales Alphabet zur Bildung gebrochener Dezimalzahlen
        T = {'0', '1', '2', '3', '4', '5','6', '7', '8', '9', '-', '.' }
        ```
3. Was ist ein nichtterminales Alphabet?
    * Die Menge der Metasymbole, die zur Bildung syntaktischer Regeln benötigt werden.
        ```java
        //Metasymbole für Dezimalzahlen
        N = { ZAHL, GANZZAHL_TEIL, GEBROCHENZAHL_TEIL}
        //Metasymbole für Deutsche Grammatik
        N = { SATZ, SUBJEKT, PRÄDIKAT, OBJEKT, ARTIKEL, VERB, SUBSTANTIV }
        ```
4. Erklären Sie den Ausdruck G = (T,N,s,P)
    * Die Grammatik (G) besteht aus:
        * T: terminales Alphabet
        * N: nicht terminales Alphabet
        * s: Startsymbol, Axiom
        * P: Menge der Produktionen (Regeln)
5. Zeichen Sie den Syntaxbaum der Grammatik der Folie 11 auf.

6. Bilden Sie einen anderen möglichen Satz aufgrund des Syntaxbaum, als auf den vorhergehenden Folien.


#### Kontrollfragen B

1. Woraus besteht eine EBNF Notation?
    * Sie besteht aus:
        * einer Startregel,
        * sonstige Regeln,
        * terminale und nichtterminale Symbole
    ```
    BNF:
    '=' : Definitionszeichen
    '|' : Alternative
    ''' : Kennzeichnungen von Sprachsymbolen
    'Φ' : Die leere Zeichenfolge
    '.' : Das Ende einer Regel
    Zusätzlich im EBNF:
    '( )' , '[ ]' , '{ }' , '< >' : Klammern
    ```
2. Wie sind terminale Symbole in EBNF darzustellen?
    * In Anführungszeihen
3. Was muss mit nichtterminale Symbole in EBNF passieren?
    * Sie müssen in Regeln erklärt werden
    * Metasymbole müssen durch regeln beschrieben werden.
4. Wie werden alternative Elemente in EBNF dargestellt?
    * Alternativen Elemente gruppiert durch das Zeichen: |
5. Wie werden sich wiederholende Elemente in EBNF dargestellt?
    * mit geschweiften Klammern __{  }__ oder was auch geht __( )+__
6. Wie werden optionale Elemente in EBNF dargestellt?
    * runde Klammer mit Fragezeichen __(  )?__ oder __[  ]__
