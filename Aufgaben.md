# Übungsaufgaben

#### Aufgaben zum Selbststudium
_Diese Aufgaben werden nicht geprüft und müssen auch nicht abegeben werden!_  
_Bei Fragen, Unklarheiten, Fehlern oder Problemen wendet euch gerne an Lukas._

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
    
## Aufgabe 3

### 3.1 Komisches Verhalten ist Komisch
```typescript
console.log(true+true);
console.log(5+1);
console.log(5+'1');
console.log('5'+1);
console.log('5'-1);
```

Betrachte den obigen Code. Was wird er auf der Konsole ausgeben und warum? Bringe ihn anschließend zum laufen und überprüfe deine Annahme.

### 3.2 Lokal vs Global
```typescript
let x: string = "Hallo";
console.log(x);
func1(x);
func2();
func3();

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
    console.log(x);
}
```

Betrachte den obigen Code. Was wird er auf der Konsole ausgeben und warum? Bringe ihn anschließend zum laufen und überprüfe deine Annahme. 

### 3.3
Erkläre den Unterschied zwischen globalen Variablen, lokalen Variablen und Übergabeparametern.  
Inwiefern unterscheiden sich diese von Funktionen?

### 3.4
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

### 3.5
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

## Aufgabe X :wrench: Kontrollstrukturen

### X.1
Ist der Ausdruck `((!a OR b) AND c) OR ((!b OR c) AND a))` true oder false für `a=true`, `b=true` und `c=false`? Schreiben Sie ein Programm, um die Frage zu beantworten.
_Hinweis: Verwenden Sie boolesche Variablen und die logischen Operatoren `&&` für AND, `!` für NOT und `||` für OR._

### X.2
Berechne mithilfe einer while Schleife alle ganzen Zahlen von 1 bis 100 und gib das Ergebnis auf der Konsole aus.

### X.3
Berechne mithilfe einer do-while Schleife den Wert von 8! (Fakultät, 0! = 1, 1!=1, 2!=1\*2, ..., 8! = 1\*2\*3\*4\*5\*6\*7\*8) und gib das Ergebnis auf der Konsole aus.

### X.4
Gebe mithilfe einer for Schleife die ersten 20 Zahlen der Fibonacci Reihe aus (0, 1, 1, 2, 3, 5, 8, 13, ...)

### X.5
Nutze eine beliebige Schleife um 10 [zufällige](https://developer.mozilla.org/de/docs/Web/JavaScript/Reference/Global_Objects/Math/math.random) Ganzzahlen auf der Konsole auszugeben.

### X.6 :star:
Schreibe eine Funktion, welche alle Primzahlen zwischen einem Minimum und einem Maximum ermittelt und auf der Konsole ausgibt. Wie hast du die Funktion getestet?

### X.7
Schreibe ein Programm, welches alle Schaltjahre von 1900 bis heute ausgibt. Ein Jahr ist ein Schaltjahr, wenn die Jahreszahl durch 4, aber nicht durch 100 teilbar ist. Sollte die Jahreszahl durch 400 teilbar sein, handelt es sich dennoch um ein Schaltjahr.

### X.8
Schreibe ein Programm, das folgende Aufgabe löst:

Auf einer Wiese hütet die Liesel ihre Gänse und anderes Kleinvieh. Der Lehrer der gerade vorbeikommt fragt Liesel nach der Anzahl ihrer Tiere. Liesel antwortet: "Ich hüte doppelt so viele Gänse wie Hühner, aber dreimal so viele Kaninchen wie Schafe. Insgesamt haben meine Tiere 90 Beine." Wie viele Tiere in welcher Gattung hütet Liesel? (Hinweis: jedes Tier hat mindestens 2 Beine, also gibt es insgesamt nicht mehr als 45 Tiere, also nicht mehr als 45 Tiere von jeder Art. Also nicht denken, sondern durchprobieren: 0, 1, ..., 45 Gänse, ... und Nebenbedingung prüfen.

### X.9
Schreibe eine Funktion, die die Rückgabe von Wechselgeld nach einem Kauf bestimmt. Sie soll zwei Zahlen entgegennehmen: den Kaufbetrag und den vom Kunden dem Kassierer gegebenen Betrag. Die Funktion soll das Wechselgeld berechnen und dabei soll eine möglichst geringe Anzahl von Banknoten und Münzen zurückgegeben werden. Gehen von der Euro-Stückelung aus (1 Cent, 2 Cent, 5 Cent, 10 Cent, ...500 €). Prüfe, ob der Kaufbetrag nicht größer ist als der gegebene Betrag. Gebe die ermittelte Stückelung des Wechselgelds auf der Konsole aus.

## Aufgabe 2 :wrench:

### 2.1 
Welche elementaren Datentypen sind dir bekannt? Welche Werte können diese speichern?  
Schreibe ein Programm welches je eine Variable für jeden Basisdatentyp deklariert, initialisiert und auf der Konsole ausgibt.

### 2.2
Was erlaubt es dem Typescript Entwickler, seine eigenen, komplexen Datentypen zu definieren?

> :information_source: Eigene Typen sollten immer sinnvolle Bezeichnungen haben. Beschreibt euer Typ eine einzelnes Haus? Dann sollte der Typ auch "Haus" und nicht "Häuser" heißen. Grundsätzlich legen wir ja einen "Bauplan" für ein einzelnes Objekt an, und erschaffen dann mehrere dieser einzelnen Objekte.

### 2.3
Stelle dir vor du willst ein System für die Hochschule entwickeln, um alle Studenten abzuspeichern und zu verwalten.

#### 2.3.1
Definiere einen komplexen Datentyp für einen solchen Studenten. Wie könnte dieser Aussehen, welche Eigenschaften sollte dieser haben?

#### 2.3.2 
Erschaffe drei verschiedene Studenten, fülle sie mit sinnvollen Werten und speichere diese in variablen ab.

#### 2.3.3
Packe diese Variablen in ein Array von Studenten _(Typisierung!)_. Außerdem, gebe auf der Konsole einige Eigenschaften der Studenten aus.

#### 2.3.4 
Schreibe eine Funktion `showInfo(...)` mit geeigneten Übergabeparametern, welche wichtige Infos über einen Studenten auf der Konsole ausgibt (z.B: "Max Mustermann, Matrikelnummer: 123456, Studiengang: MUM, ....").

Rufe diese Funktion einmal für jeden Studenten auf.


## Aufgabe 4

### 4.1
Schreibe ein Funktion mit der Signatur `add(a: number, b: number): number` welche die zwei übergebenen Zahlen a und b zusammenzählt und das Ergebnis zurück gibt.

Bringe anschließend den folgenden code zum laufen.

```typescript
console.log(add(5,3));
let a: number = 17;
let b: number = 25;
let c: number = add(a,b);
console.log(c);
```

### 4.2 
Schreibe eine Funktion mit der Signatur `divideable(a: number, b:number): boolean` welche dann `true` zurück geben soll, wenn die erste Zahl ohne Rest durch die zweite Zahl teilbar ist. Prüfe die Funktion mit einem eigenen Testprogramm.

### 4.3 :star:
Schreibe eine Funktion mit der Signatur `ggT(a: number, b:number): number` welche den größten gemeinsamen Teiler der beiden übergebenen Variablen zurück gibt.

### 4.4 :star:
Schreibe eine Funktion mit der Signatur `kgV(a:number, b:number): number` welche das kleinste gemeinsame Vielfache der beiden übergebenen Zahlen zurück gibt. Inwiefern hängen Aufgabe 4.3 und 4.4 zusammen?

## Aufgabe X :star:

Bei diesen Aufgaben geht es um Arraymanipulation. Für jede Unteraufgabe soll eine eigene Funktion erstellt werden welche die zu verarbeitenden Arrays als Parameter entgegen nimmt, verarbeitet und das Ergebnis zurück gibt. Geht von Number Arrays aus. _Die meisten dieser Aufgaben/Funktionen sind in der generischen Array Klasse bereits implementiert. Diese eingebauten Funktionen sollen hier gerade NICHT verwendet, sondern selbst geschrieben werden. Außerdem muss darauf geachtet werden, dass die übergebenen Arrays nicht verändert werden, sondern ein neues Array angelegt und verändert wird!_

> :information_source: Hier ist die Differenzierung zwischen Call by Value und Call by Reference wichtig zu verstehen. [Zum nachlesen.](https://medium.com/nodesimplified/javascript-pass-by-value-and-pass-by-reference-in-javascript-fcf10305aa9c)

### X.1
Eine Funktion `backwards(...)`, welche ein Array entgegen nimmt und rückwärts zurück gibt.

### X.2  
Eine Funktion `join(...)` die zwei Arrays zusammenfügt, indem es das zweite hinter das erste hängt.

### X.3
Eine Funktion `split(...)` die ein Array und zwei indexe entgegen nimmt und das Array zwischen diesen beiden Indexen zurück gibt. _Bonus: Hier wäre eine Prüfung der übergebenen Indizes angebracht. Welche Prüfungen sind dies? Implementiere das auch._

### X.4 :star2:
Eine Funktion `sort(...)` welche das übergebene Array sortiert zurück gibt. _Bonus: ein weiterer Übergabeparameter der darüber entscheiden soll, ob aufsteigend oder absteigend sortiert werden soll. Standardmäßig soll dieser auf "aufsteigend" stehen. :dizzy:_
> :information_source: [Optionale und Standard Parameter](https://medium.com/@kgrvr/typescript-functions-optional-parameters-b245e7a06d7d)

### X.5
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

## Aufgabe Y

### Y.1
