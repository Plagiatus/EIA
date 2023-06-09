# Übungsaufgaben

#### Aufgaben zum Selbststudium
_Diese Aufgaben werden nicht geprüft und müssen auch nicht abegeben werden!_  
_Bei Fragen, Unklarheiten, Fehlern oder Problemen wendet euch gerne an Lukas._

Die :information_source: Blöcke sind nicht nur für die Aufgabe interessant.

Die Aufgaben sind nur bedingt sortiert. Solltet ihr also bei einer Aufgabe nicht weiter kommen, versucht es mit der nächsten. Auch Teilaufgaben haben nicht immer etwas miteinander zu tun.

Aufgaben teilweise inspiriert von oder nur leicht verändert übernommen von Prof. Dr. F. Kaspar der Fakultät Informatik der HFU.

## [Lösungen](https://github.com/Plagiatus/EIA/blob/master/Lösungen.md)

Symbol | Bedeutung
-----|-----
nichts | Standard Aufgabe. Sollte gut lösbar sein.
:wrench: | Grundlagen Aufgabe. Dient der Wiederholung und dem Verständis
:star: | Fortgeschrittene Aufgabe. Etwas schwieriger aber mit dem aktuellen Wissen machbar
:star2: | Schwierige Aufgabe. Erfordert eigene Recherche oder besonders kreative Umsetzung mit für euch neuen Konzepten.
:dizzy: | Weiterführende Aufgabe. Erfordert Konstruke die euch so noch nicht bekannt sind. Ein Link zu diesen zum Selbststudium ist beigefügt.
:information_source: | Weiterführende Informationen zu einem Thema oder einer Aufgabe.
:warning: | Wichtige Hinweise


> :information_source: Fast alle dieser Aufgaben sollten ohne oder nur mit minimalem Nutzerinput funktionieren. Sofern nicht explizit angegeben, sollten die Funktionen automatisch ablaufen und **nicht** über Buttons o.ä. aufgerufen werden.  
In der zugehörigen HTML Datei sollte nur das Minimum einer HTML5 Datei sowie die Einbindung der Javascript Datei(en) vorhanden sein. Darum empfehle ich auch, für jede Aufgabe eigene Dateien anzulegen und nicht zu versuchen das alles in eine Datei zu quetschen.

> :warning: Versucht so viel es geht mit Übergabeparametern zu arbeiten und diese auch zu nutzen. **Greift nicht in euren Funktionen auf die globalen Variablen zu, wenn ihr eine lokale Variable habt mit der ihr arbeiten könnt!**


## Aufgabe 1 :wrench:

```typescript
namespace A1 {
    function main(): void {
        let x: string = "Alles";
        console.log(x);
        func1();
        console.log("Logo!");
    }
    
    main();

    function func1(): void {
        console.log("Klar?");
    }
}
```

### 1.1
Bringe das obige Programm zum Laufen und experimentiere mit den Namen der Variablen und Funktionen. Welche Variablennamen sind nicht zulässig, welche sind zulässig?  

### 1.2
Öffnet im Browser den Debugger (neben der Konsole) und setzt einen Breakpoint in Zeile 3. Ladet dann die Seite neu und geht Schritt für Schritt durch den Code durch, die Schaltflächen dafür sind normalerweise rechts am Rand:  
![](https://i.imgur.com/SVnLY0p.png)

> :information_source: Ein Debugger dient wie der Name schon vermuten lässt dem Debuggen, dem Entfernen von Bugs, dem Finden und Erkennen von Fehlern. Er erlaubt es einem, ein Programm zu pausieren und dieses dann Zeile für Zeile durchzuführen um den Ablauf und die Änderungen die während des Durchlaufs passieren, nachzuvollziehen. Diese langsame und Schritt für Schritt Vorgehensweise erlaubt es relativ einfach die internen Vorgänge nachzuvollziehen und Fehler in der Logik des Programms zu finden. Er ist also neben Konsolenausgaben das wichtigste und wertvollste Tool zur Fehlererkennung.

>> Der Name "Bug" stammt Gerüchten nach daher, dass in den ersten elektronischen Rechnern die mechanischen Kontake nicht mehr zusammengedrückt werden konnten, weil ein Käfer seinen Weg in den Zwischenraum gefunden hat, wodurch sich die Maschine verrechnet hat.

> :information_source: Bei vielen Programmiersprachen ist der Debugger direkt in der IDE (in unserem Fall VSCode) integriert, aber um Javascript Code ausführen zu können benötigt man entweder einen Browser oder einen Server, was das Debuggen deutlich schwieriger macht. Glücklicherweise steht uns in Browsern ein Debugger zur Verfügung.

### 1.3
Füge weitere Funktionen ein, die wie `func1()` jeweils ein Wort ausgeben. func1 kann kopiert werden. Rufe die Funktionen in `main()` auf, so dass der Text "Alles Gute! Alles klar? Alles Logo!" auf der Konsole ausgegeben wird.

### 1.4
```typescript
namespace A1_4 {
    function main(): void {
        let i: number = 9;

        do {
            console.log(i);
            i = i - 1;
        } while( i > 0);
    }

    main();
}
```

Schaue dir den obigen Code an und versuche nur durch lesen zu verstehen was passiert. Was wird auf der Konsole ausgegeben? Wann verändert sich was?  
Bringe dann den Code zum laufen und überprüfe, ob du richtig liegst. Schaue dir den Programmablauf mit dem Debugger an.

### 1.5
Baue in den Code von 1 und 1.4 Fehler ein und studiere die Fehlermeldungen. Lässt sich aus der Fehlermeldung schließen, was falsch ist?

> :information_source: Um die Fehlermeldung von VSCode zu sehen, einfach mit der Maus über die hervorgehobene Stelle fahren. Oder bei aktiviertem Watcher abspeichern, so werden die Fehlermeldungen auch in der Konsole ausgegeben.

> :warning: **Es sollte immer der erste Fehler in der Datei repariert werden, da in vielen Fällen die nachfolgenden Fehler aus den früheren Fehlern resultieren!**

#### 1.5.2
Tut euch mit einem Komilitonen zusammen und versucht die Fehler die der andere eingebaut hat zu finden.  
1.) Durch Codeinspektion: Versucht durch Lesen die Fehler zu finden.  
2.) Durch Fehlermeldungen: Schaut euch die Fehler in VSCode an und versucht diese zu verstehen.  
3.) Durch Auskommentieren und Debugger: Wenn das Programm sich übersetzen lässt aber nicht das richtige Verhalten aufweist, kommentiert nach und nach Codeschnipsel aus und wieder ein, bis ihr den Auslöser gefunden habt.  
4.) Wenn das alles nicht hilft, vergleicht mit dem vorgegebenen Code und findet die Fehler  
    
## Aufgabe 2

### 2.1 Komisches Verhalten ist Komisch
```typescript
console.log(true+true);
console.log(5+1);
console.log(5+'1');
console.log('5'+1);
console.log('5'-1);

//BONUS:
console.log(('b' + 'a' + + 'a' + 'a').toLowerCase());
```

Betrachte den obigen Code. Gibt es Fehler? Was wird er auf der Konsole ausgeben und warum? Bringe ihn anschließend zum laufen und überprüfe deine Annahme (eventuelle Fehler auskommentieren).

> :information_source: Bei einigen dieser Anweisungen sollte der Compiler Fehler ausgeben und euch den Code nicht übersetzen. Zum Glück, denn diese Anweisungen sind alle legitim in Javascript und führen zu den komischsten Ergebnissen. Typescript versucht uns vor solchen Dingen zu schützen.   
> Wer sich eine ganze Liste mit komischem Verhalten von JS als quiz verpackt anschauen will, kann hier vorbei schauen: https://jsisweird.com/

### 2.2 Lokal vs Global
```typescript
let x: string = "Hallo";
console.log(x);
func1(x);
console.log(x);
func2();
func3();
console.log(x);

function func1(y: string): void{
    y = "Bla";
    console.log(y);
}

function func2(): void{
    let x: string = "Blubb";
    console.log(x);
}

function func3(): void{
    x = "Test";
}
```

Betrachte den obigen Code. Was wird er auf der Konsole ausgeben und warum? Bringe ihn anschließend zum laufen und überprüfe deine Annahme. 

### 2.3
Erkläre den Unterschied zwischen globalen Variablen, lokalen Variablen und Übergabeparametern.  
Inwiefern unterscheiden sich diese von Funktionen?

### 2.4
```typescript
let zahl: number = 3;

main();

function main() : void{
    let zahl: number;
    f1();
    console.log(zahl);
}

function f1(): void {
    console.log(zahl);
    f2();
}

function f2(): void {
    let zahl: number = 7;
    console.log(zahl);
}
```

Betrachte den obigen Code. Was wird er auf der Konsole ausgeben und warum? Bringe ihn anschließend zum laufen und überprüfe deine Annahme.

### 2.5
```typescript
let i: number;
let resultat: number;
let s: string = "";

for(i = 1; i < 7; i++){
    s += i + "\t";
}
console.log(s);

s = "";
for(i = 9; i > 2; i--){
    s += i + "\t";
    s += i*i + "\n";
}
console.log(s);

resultat = 0;
for(i=1; i < 11; i = i + 2) {
    resultat = resultat + 1;
    console.log("Zwischensumme: " + resultat);
}
```

Betrachte den obigen Code. Was wird er auf der Konsole ausgeben und warum? Bringe ihn anschließend zum laufen und überprüfe deine Annahme.

## Aufgabe 3 :wrench: Kontrollstrukturen

### 3.1
Ist der Ausdruck `((NOT a OR b) AND c) OR ((NOT b OR c) AND a)` true oder false für `a=true`, `b=true` und `c=false`? Schreibe ein Programm, um die Frage zu beantworten.
_Hinweis: Verwende boolesche Variablen und die logischen Operatoren `&&` für AND, `!` für NOT und `||` für OR._

### 3.2
Zähle mithilfe einer while Schleife alle ganzen Zahlen von 1 bis 100 zusammen und gib das Ergebnis auf der Konsole aus.

### 3.3
Berechne mithilfe einer do-while Schleife den Wert von 8! (Fakultät, 0! = 1, 1!=1, 2!=1\*2, ..., 8! = 1\*2\*3\*4\*5\*6\*7\*8) und gib das Ergebnis auf der Konsole aus.

### 3.4
Gebe mithilfe einer for Schleife die ersten 20 Zahlen der Fibonacci Reihe aus (0, 1, 1, 2, 3, 5, 8, 13, ...)

### 3.5
Nutze eine beliebige Schleife um 10 [zufällige](https://developer.mozilla.org/de/docs/Web/JavaScript/Reference/Global_Objects/Math/math.random) Ganzzahlen auf der Konsole auszugeben.

### 3.6 :star:
Schreibe eine Funktion, welche alle Primzahlen zwischen einem Minimum und einem Maximum ermittelt und auf der Konsole ausgibt. Wie hast du die Funktion getestet?

### 3.7
Schreibe ein Programm, welches alle Schaltjahre von 1900 bis heute ausgibt. Ein Jahr ist ein Schaltjahr, wenn die Jahreszahl durch 4, aber nicht durch 100 teilbar ist. Sollte die Jahreszahl durch 400 teilbar sein, handelt es sich dennoch um ein Schaltjahr.

### 3.8 :star:
Schreibe ein Programm, das folgende Aufgabe löst:

Auf einer Wiese hütet die Liesel ihre Gänse und anderes Kleinvieh. Der Lehrer der gerade vorbeikommt fragt Liesel nach der Anzahl ihrer Tiere. Liesel antwortet: "Ich hüte doppelt so viele Gänse wie Hühner, aber dreimal so viele Kaninchen wie Schafe. Insgesamt haben meine Tiere 90 Beine." Wie viele Tiere in welcher Gattung hütet Liesel? _(Hinweis: jedes Tier hat mindestens 2 Beine, also gibt es insgesamt nicht mehr als 45 Tiere, also nicht mehr als 45 Tiere von jeder Art. Also nicht denken, sondern durchprobieren: 0, 1, ..., 45 Gänse, ... und Nebenbedingung prüfen.)_

### 3.9 :star:
Schreibe eine Funktion, die die Rückgabe von Wechselgeld nach einem Kauf bestimmt. Sie soll zwei Zahlen entgegennehmen: den Kaufbetrag und den vom Kunden dem Kassierer gegebenen Betrag. Die Funktion soll das Wechselgeld berechnen und dabei soll eine möglichst geringe Anzahl von Banknoten und Münzen zurückgegeben werden. Gehe von der Euro-Stückelung aus (1 Cent, 2 Cent, 5 Cent, 10 Cent, ...500 €). Prüfe, ob der Kaufbetrag nicht größer ist als der gegebene Betrag. Gebe die ermittelte Stückelung des Wechselgelds auf der Konsole aus.

## Aufgabe 4 :wrench:

### 4.1 
Welche elementaren Datentypen sind dir bekannt? Welche Werte können diese speichern?  
Schreibe ein Programm welches je eine Variable für jeden Basisdatentyp deklariert, initialisiert und auf der Konsole ausgibt.

### 4.2
Was erlaubt es dem Typescript Entwickler, seine eigenen, komplexen Datentypen zu definieren?

> :information_source: Eigene Typen sollten immer sinnvolle Bezeichnungen haben. Beschreibt euer Typ eine einzelnes Haus? Dann sollte der Typ auch "Haus" und nicht "Häuser" heißen. Grundsätzlich legen wir ja einen "Bauplan" für ein einzelnes Objekt an, und erschaffen dann mehrere dieser einzelnen Objekte.

### 4.3
Stelle dir vor du willst ein System für die Hochschule entwickeln, um alle Studenten abzuspeichern und zu verwalten.

#### 4.3.1
Definiere einen komplexen Datentyp für einen solchen Studenten. Wie könnte dieser Aussehen, welche Eigenschaften sollte dieser haben?

#### 4.3.2 
Erschaffe drei verschiedene Studenten, fülle sie mit sinnvollen Werten und speichere diese in variablen ab.

#### 4.3.3
Packe diese Variablen in ein Array von Studenten _(Typisierung!)_. Außerdem, gebe auf der Konsole einige Eigenschaften der Studenten aus.

#### 4.3.4 
Schreibe eine Funktion `showInfo(...)` mit geeigneten Übergabeparametern, welche wichtige Infos über einen Studenten auf der Konsole ausgibt (z.B: "Max Mustermann, Matrikelnummer: 123456, Studiengang: MUM, ....").

Rufe diese Funktion einmal für jeden Studenten auf.


## Aufgabe 5

### 5.1
Schreibe ein Funktion mit der Signatur `add(a: number, b: number): number` welche die zwei übergebenen Zahlen a und b zusammenzählt und das Ergebnis zurück gibt.

Bringe anschließend den folgenden code zum laufen.

```typescript
console.log(add(5,3));
let a: number = 17;
let b: number = 25;
let c: number = add(a,b);
console.log(c);
```

### 5.2 
Schreibe eine Funktion mit der Signatur `divideable(a: number, b:number): boolean` welche dann `true` zurück geben soll, wenn die erste Zahl ohne Rest durch die zweite Zahl teilbar ist. Prüfe die Funktion mit einem eigenen Testprogramm.

### 5.3 :star:
Schreibe eine Funktion mit der Signatur `ggT(a: number, b:number): number` welche den größten gemeinsamen Teiler der beiden übergebenen Variablen zurück gibt.

### 5.4 :star:
Schreibe eine Funktion mit der Signatur `kgV(a:number, b:number): number` welche das kleinste gemeinsame Vielfache der beiden übergebenen Zahlen zurück gibt. Inwiefern hängen Aufgabe 5.3 und 5.4 zusammen?

### 5.5 
Schreibe eine Funktion welche die Zahlen 1/2, 1/4, 1/8, 1/16, ... aufsummiert und das Ergebnis zurück gibt, in zwei Varianten:

#### 5.5.1
Als Übergabeparameter erhält die Funktion eine Zahl, die angibt, wie viele Summanden für die Summe berücksichtigt werden sollen. Zum Beispiel bedeutet die Übergabe von 20, dass der letzte berücksichtigte Summand 1/2<sup>20</sup> ist.

#### 5.5.2
Als Übergabeparameter erhält die Funktion eine Zahl für die Genauigkeit (z.B. epsilon=0.001) mit der die Summe berechnet werden soll. Es soll so lange summiert werden, bis gilt summand < epsilon, wobei summand=1/2n, mit n=1,2,3,4,5,...

## Aufgabe 6 :star:

Bei diesen Aufgaben geht es um Arraymanipulation. Für jede Unteraufgabe soll eine eigene Funktion erstellt werden welche die zu verarbeitenden Arrays als Parameter entgegen nimmt, verarbeitet und das Ergebnis zurück gibt. Geht von Number Arrays aus. _Die meisten dieser Aufgaben/Funktionen sind in der generischen Array Klasse bereits implementiert. Diese eingebauten Funktionen sollen hier gerade NICHT verwendet, sondern selbst geschrieben werden. Außerdem muss darauf geachtet werden, dass die übergebenen Arrays nicht verändert werden, sondern ein neues Array angelegt und verändert wird!_

> :warning: Hier ist die Differenzierung zwischen Call by Value und Call by Reference wichtig zu verstehen. [Zum nachlesen.](https://medium.com/nodesimplified/javascript-pass-by-value-and-pass-by-reference-in-javascript-fcf10305aa9c)

### 6.1
Eine Funktion `backwards(...)`, welche ein Array entgegen nimmt und rückwärts zurück gibt.

### 6.2  
Eine Funktion `join(...)` die zwei Arrays zusammenfügt, indem es das zweite hinter das erste hängt.

### 6.3
Eine Funktion `split(...)` die ein Array und zwei indexe entgegen nimmt und das Array zwischen diesen beiden Indexen zurück gibt. _Bonus: Hier wäre eine Prüfung der übergebenen Indizes angebracht. Welche Prüfungen sind dies? Implementiere das auch._

### 6.4 :star2:
Eine Funktion `sort(...)` welche das übergebene Array sortiert zurück gibt. _Bonus: ein weiterer Übergabeparameter der darüber entscheiden soll, ob aufsteigend oder absteigend sortiert werden soll. Standardmäßig soll dieser auf "aufsteigend" stehen. :dizzy:_
> :information_source: [Optionale und Standard Parameter](https://medium.com/@kgrvr/typescript-functions-optional-parameters-b245e7a06d7d)

### 6.5
Wenn alle obigen Aufgaben erfüllt worden sind, sollte folgender Code problemlos laufen. Werden die richtigen Ausgaben ausgegeben?
```typescript
let arr: number[] = [5, 42, 17, 2018, -10, 60, -10010];
let arrBack: number[] = backwards(arr);
console.log(arr);
console.log(arrBack);
console.log(join(arr,[15, 9001, -440]);
arr = split(arr,0,4);
console.log(arr);
console.log(split(arr,1,2);

//Wenn Teilaufgabe 4 gemacht wurde
console.log(sort(arr));
```

## Aufgabe 7 :star:

### 7.1
Programmiere einen Stapel (Stack) für Zahlen. Stapel bedeutet, das zuletzt eingefügte Element wird zuerst entfernt. Dem Stack sollen Elemente hinzugefügt sowie entnommen werden können. Beginne mit dem Einfügen an Stelle 0 des Arrays. Ggf sollte eine Variable zur aktuellen Anzahl der Elemente im Array verwaltet werden. Dadurch kann die Position zum Einfügen eines neuen sowie zurückgeben des aktuellsten Elements definiert. Berücksichtige den Fall, dass aus einem leeren Stapel kein Element entnommen werden kann.
Wie hast du das Programm getestet?

#### 7.1.1 
Wie ändert sich der Code wenn der Stapel eine maximale Größe von 10 Elementen haben soll? Bedenke hier auch, dass einem vollen Stapel nichts mehr hinzugefügt werden kann. 

### 7.2
Schreibe ein Programm zur Ermittlung der ersten 1000 Primzahlen. Merke dir die gefundenen Primzahlen in einem Array. Beginne mit der Primzahl 2 an der Stelle 0 im Array. Prüfe alle Zahlen beginnend mit 3. Prüfe jede neue Zahl ob sie prim ist, indem du sie durch jede vorherige gefundene Primzahl teilst. Ist die Zahl durch keine vorherige Primzahl teilbar, so ist sie prim. Speichere diese Zahl in das Array. Gebe die 1000ste Primzahl auf der Konsole aus.  
_In dieser Aufgabe gibt es eine große Chance für Optimierung, indem man aufhört, die Zahlen zu testen, nachdem man eine gefunden hat, durch die die zu testende Zahl teilbar ist. Wenn du kannst, versuche das mit einzubauen._

### 7.3
Schreibe _je eine Funktion_, welche eine übergebene Zeichenkette analysiert/verarbeitet. 

#### 7.3.1 :star2:
Bestimme die Anzahl der Vokale (a, e, i, o, u) in einer Zeichenkette (Kleinbuchstaben ohne Umlaute genügen). Hierzu kann auf die einzelnen Zeichen der string Variable wie in einem Array (string[index]) oder mit der Funktion string.charAt(index) zugegriffen werden. Gebe das Ergebnis auf der Konsole aus.  
_Hinweis: Die Verwendung eines Switch Statements bietet sich hier an._

#### 7.3.2 :dizzy:
> :information_source: Jedes Zeichen in einer Zeichenkette ist nicht einfach nur ein Zeichen, sondern kann mithilfe von [ASCII Codierung](http://www.asciitable.com/) in einen Zahlenwert umgewandelt werden (und natürlich auch wieder zurück). Diese Codes können in Typescript mithilfe von der Funktion [charCodeAt](https://www.tutorialspoint.com/typescript/typescript_string_charcodeat.htm) ausgelesen und mit der Funktion [String.fromCharCode](https://developer.mozilla.org/de/docs/Web/JavaScript/Reference/Global_Objects/String/fromCharCode) zurück gewandelt werden. Der Buchstabe A entspricht dabei 65, der Buchstabe a der 97.

Schreibe eine Funktion, welche einen string entgegen nimmt und mithilfe der Funktionen `charCodeAt` und `fromCharCode` alle Großbuchstaben in ihre zugehörigen Kleinbuchstaben umwandelt. Alle andere Zeichen sollen dadurch nicht beeinflusst werden. Gebe den resultierenden String zurück. (Die eingebauten Funktionen eines Strings wie "toLowerCase" sollen logischerweise nicht verwendet werden).

#### 7.3.3 :dizzy:
Verschlüssle den übergebenen String mit einer sogenannten [Caesar-Verschlüsselung](https://de.wikipedia.org/wiki/Caesar-Verschl%C3%BCsselung), indem die Buchstaben alle um einen Wert weiter verschoben werden (a -> b, b -> c, ... y -> z, z -> a). Nutze hierfür die ASCII Codierung. Beispiel: aus hal wird ibm. Gebe das Ergebnis auf der Konsole aus und aus der Funktion zurück. Um die Sache etwas zu vereinfachen kannst du die Verschlüsselung auch nur auf Kleinbuchstaben beschränken.

#### 7.3.4 :dizzy:
Schreibe eine Entschlüsselung für den in 7.3.3 geschriebenen String, so dass nach Verschlüsselung und Entschlüsselung wieder der originale Text zu sehen ist. Gebe das Ergebnis auf der Konsole aus und aus der Funktion zurück.

#### 7.3.5 :dizzy:
Erweitere das Verfahren aus 7.3.3 und 7.3.4 auf eine beliebige Zeichenrotation und übergebe die Rotationsmenge als Funktionsparameter.  

> ```C=(T-'A'+ n)%26+'A'```  
> C=Cypherzeichen, T=Klartextzeichen, jeweils ASCII Code, Rotation um n Buchstaben.  
> Beispiel: (C=('B'-'A'+ 5 )%26+'A'='G' )

> :information_source: Dies nennt man auch eine Cäsar-Chiffre

### 7.4 :star2:

> :information_source: Eine rekursive Funktion ist eine Funktion, welche sich selbst erneut aufruft. Dies eröffnet viele neue Möglichkeiten der Programmierung. Beispiel: 
```typescript
f1(0);
function f1(a:number){
    if(a < 5) 
    {
        f1(a+1);
    }
    console.log(a);
}
```

Ein klassisches Beispiel für eine rekursive Funktion ist die Fakultät:  
fakultaet(n+1) = (n+1) * fakultaet(n), fakultät(0)=1.  
Es gilt n>=0. Programmiere die Fakultät über eine rekursive Funktion.

### 7.5 :star2:
In einer vorherigen Aufgabe haben wir die Fibonacci Reihe schon iterativ berechnet. Berechne jetzt die n-te Fibonacci Zahl rekursiv. Rekursive Definition der Fibonacci Reihe: f(n):=f(n-1)+f(n-2) mit den Abbruchbedingungen f(1)=1 und f(0)=0;

## Aufgabe 8 :dizzy: Schachbrett

> :information_source: In einem Array kann ein beliebiger Datentyp gespeichert werden. Dies gilt sowohl für die bereits vordefinierten (number, string, etc) wie auch für selbst definierte (interface, class). Ein Array ist allerdings auch ein Datentyp. Dies hat zur Folge, dass wir in unserem Array auch Arrays speichern können. Hier ist dann die Rede von [mehrdimensionalen Arrays](https://www.tutorialspoint.com/typescript/typescript_multi_dimensional_arrays.htm). Die Zugriffsweise ist intuitiv ähnlich wie bei einem eindimensionalem Array: array[0][1] greift auf das zweite Element aus dem Array zu, welches im ersten Element gespeichert ist.

Definiere ein zweidimensionales Array als Schachbrett, also 8 Felder hoch und 8 Felder breit. Als Datentyp wählen wir zunächst boolean, so dass in unseren Feldern entweder true oder false stehen kann. Zu beginn sollten alle Felder mit false initialisiert werden (hier würde sich eine verschachtelte Schleife anbieten).

### 8.1
Finde eine geeignete Methode um das Ergebnis der folgenden Aufgaben zu visualisieren. Entweder über eine gut formatierte Konsolenausgabe oder mehr visuelle Ausgabe auf der Seite (komplexer!).

### 8.2
Ein Turm kann sich im Schach nur gerade bewegen, entweder waagrecht oder senkrecht. Schreibe eine Funktion welche eine Position in Form von zwei Variablen für das Schachbrett entgegen nimmt und alle möglichen neuen Positionen innerhalb des Schachbretts für den Turm auf true setzt. Gebe das Ergebnis aus.

### 8.3
Ein Pferd kann sich im Schach immer zwei Felder in einer geraden Linie, mit anschließend einem Feld nach links oder rechts bewegen. Wiederholen sie die Aufgabe 8.2 mit einem Springer/Pferd.

### 8.4 :dizzy: :dizzy:
Als [Springerproblem](https://de.wikipedia.org/wiki/Springerproblem) wird das Problem bezeichnet, einen Springer/Pferd auf einem leeren Schachbrett so hin und her zu ziehen, dass jedes Feld genau einmal besucht wird. Schreibe ein Programm das zu einer gegebenen Position versucht, diese Route zu finden. _Zusatz :dizzy:: finde eine Möglichkeit die Reihenfolge der Schritte anzuzeigen, oder diese in form der Ausgabe von oben sogar "nachzuspielen"._

> :warning: Ein einfacher Backtracking Algorithmus ist die algorithmisch einfachste Lösung, allerdings kann dieser **SEHR LANGE** dauern (so lange um genau zu sein, dass euer Browser wahrscheinlich vorher abstürzt). Ich empfehle darum entweder ein kleineres Feld als 8x8 zu nutzen oder einen etwas schlaueren Algorithmus zu verwenden (z.B. Warnsdorf), wobei ich euch letzteres eher ans Herz legen würde. Zur Vorarbeit kann zunächst ein einfacher Backtracking Algorithmus verwendet und dieser dann umgeschrieben werden. 
> :information_source: Um eine javascript datei ohne Browser auszuführen, kann ein _Nodeserver_ verwendet werden. Wenn ihr Typescript nutzt, habt ihr Node bereits installiert und könnt darum in der Konsole den Befehl `node pfad/zur/javascript/datei.js` verwenden. Zum Beenden dieses Servers die Tastenkombination STRG+C drücken.

**Lösungshinweise:**  
Am besten lösbar ist dieses Problem über rekursive Funktionen.  
Auch dieses Problem lässt sich am besten durch ausprobieren und nicht durch nachdenken lösen. Lass den Springer sich so lange bewegen, bis es keine weitere Möglichkeit gibt sich weiter zu bewegen. Wenn alle Felder abgedeckt sind, ist eine Lösung gefunden. Hat sich der Algorithmus in eine Ecke bewegt, mache den letzten Schritt ungeschehen und versuche einen anderen Weg. Führt auch dieser in eine Sackgasse mache ihn ungeschehen und versuche einen anderen Weg.  
Ein Springer hat bis zu 8 verschiedene Bewegungsmöglichkeiten. Wie können diese programmatisch und im Bezug auf ein zweidimensionales Array dargestellt werden?

## Aufgabe 9 :dizzy: :dizzy: :dizzy: Taschenrechner

Programmiere einen Taschenrechner. Lege dazu im HTML Dokument ein Textinput Feld, einen "Berechnen" Knopf sowie ein Bereich für das Ergebnis an. Stelle sicher, dass du auf all diese Elemente einfach aus dem Code zugreifen kannst (z.B. über IDs und GetElementById). Füge über `addEventListener` den Button einen Klick-Listener hinzu, welcher die die Funktion zur Auswertung aufruft.  
Im Textinput Feld soll der Nutzer einen beliebigen (nach unseren Regeln gültigen) Ausdruck eingeben können, welcher dann von unserem Programm ausgewertet wird. Zulässige Elemente des Ausdrucks sind Ganzzahlkonstanten, Trennzeichen, die Klammern ( und ) und die binären Operatoren +, -, \*, / und %.  
Ein Beispiel für einen gültigen Ausdruck: `(1+3)\*89+27%2-(567/45)`. Leerzeichen sollen erlaubt sein.

**Lösungshinweise:**  
In einem ersten Schritt müssen der Ausdruck geparst, d.h. die Elemente des Ausdrucks (Konstanten, Operatoren, Klammern) identifiziert werden. Eine switch Anweisung ist hier eine gute Wahl. Ein Array vom typ string ist eine einfache Möglichkeit, die Elemente zu speichern. 
Im zweiten Schritt muss der Ausdruck als Baumstruktur aufbereitet werden. An der Wurzel steht ein Operator, dieser verknüpft zwei Operanden. Die einwertigen Operanden + und – berücksichtigen wir nicht. Der Ausdruck: `+3` wäre also ein ungültiger Ausdruck. Die Konstanten bilden die Blätter des Baums. Die Operatoren bilden die inneren Knoten des Baumes. Dabei muss die Prioritäten der Operatoren (Punktrechnung vor Strichrechnung) und die Klammern berücksichtigt werden. Bei gleicher Priorität ist das Verhalten undefiniert. Darum muss man sich also nicht kümmern.  
Im dritten Schritt wird der Baum ausgewertet, d.h. reduzieren von den Blättern, bis nur noch eine Konstante übrig ist.
