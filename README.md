# Programming Concepts & Paradigms

 <i style=float:right;>Luca Dias</i> <br>

## Notes SW 1.1

___
<i style=float:right;>Donnerstag, 20. Sep</i>
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
