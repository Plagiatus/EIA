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

## Aufgabe 2 :wrench:

### 2.1 
Welche elementaren Datentypen sind dir bekannt? Welche Werte können diese speichern?

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


## Aufgabe 3

### 3.1
```typescript

```

Betrachte den obigen Code. Was wird er auf der Konsole ausgeben und warum? Bringe ihn anschließend zum laufen und überprüfe deine Annahme.

### 3.2
```typescript

```

Betrachte den obigen Code. Was wird er auf der Konsole ausgeben und warum? Bringe ihn anschließend zum laufen und überprüfe deine Annahme. 

## Aufgabe 4

### 2.1
Schreibe ein Funktion mit der Signatur `add(a: number, b: number): number` welche die zwei übergebenen Zahlen a und b zusammenzählt und das Ergebnis zurück gibt.

### 2.2 

