# Lösungen

_Die Lösungen sind noch in Arbeit und kommen hoffentlich nach und nach._

### :information_source: Die hier angegebenen Lösungen sind nur _eine_ von vielen.
Programmieren ist ein kreativer Prozess mit mehr als einer Lösung. Wir versuchen selbstverständlich euch die einfachste und am besten verständliche Lösung zu präsentieren, aber das gelingt meistens nicht. :wink:


## Aufgabe 1
### 1.1
Variablennamen können nicht mit Zahlen beginnen oder nur aus Zahlen bestehen. Leerzeichen können nicht genutzt werden. Einige Sonderzeichen (die von der Sprache reservierten) können nicht genutzt werden. Namen dürfen nicht sprach-reservierte Wörter (wie let, var, function, etc) sein.

### 1.2 
Keine Lösung nötig

### 1.3

```typescript
function main(): void {
    let x: string = "Alles";
    console.log(x);             //Alles
    func2();                    //Gute
    console.log(x);             //Alles
    func1();                    //Klar
    console.log(x);             //Alles
    func3();                    //Logo
}

main();

function func1(): void {
    console.log("Klar?");
}

function func2(): void {
    console.log("Gute!");
}

function func3(): void {
    console.log("Logo!");
}
  ```
  
  
### 1.4
Keine Lösung nötig

### 1.5
Keine Lösung nötig

### :information_source: Die hier angegebenen Lösungen sind nur _eine_ von vielen.
Programmieren ist ein kreativer Prozess mit mehr als einer Lösung. Wir versuchen selbstverständlich euch die einfachste und am besten verständliche Lösung zu präsentieren, aber das gelingt meistens nicht. :wink:

## Aufgabe 2
### 2.1
```typescript
// console.log(true+true);  // Error des Compilers in TS. In JS: 2
console.log(5+1);           // 6
console.log(5+'1');         // 51
console.log('5'+1);         // 51
// console.log('5'-1);      // Error des Compilers in TS. In JS: 4
```

### 2.2

```
Hallo
Bla
Hallo
Blubb
Test
```

### 2.3
Variablen haben eine Sichtbarkeit die bestimmt, was alles auf sie zugreifen kann und was nicht. Alles und jeder kann auf globale Variablen zugreifen, die Sichtbarkeit ist also das gesammte Programm. Lokale Variablen dagegen sind nur in dem Block sichtbar, in dem sie deklariert worden sind. Lokale Variablen haben eine höhere Priorität als globale, d.h. wenn eine lokale und eine globale Variable den selben Namen tragen, so wird der Code die lokale Variable nutzen.  
Übergabeparameter sind lokale Variablen, welche zusätzlich die Funktion haben, Werte an eine Funktion zu übergeben.

Funktionen sind Aktivitäten welche Funktionalität haben. Sie können Eingaben (Übergabeparameter) verarbeiten und außerdem Werte zurückgeben. In letzterer Hinsicht können sie wie eine Variable genutzt werden.

### 2.4 
```
3
7
undefined
```

### 2.5
```
1	2	3	4	5	6

9	81
8	64
7	49
6	36
5	25
4	16
3	9

Zwischensumme: 1
Zwischensumme: 2
Zwischensumme: 3
Zwischensumme: 4
Zwischensumme: 5
```

### :information_source: Die hier angegebenen Lösungen sind nur _eine_ von vielen.
Programmieren ist ein kreativer Prozess mit mehr als einer Lösung. Wir versuchen selbstverständlich euch die einfachste und am besten verständliche Lösung zu präsentieren, aber das gelingt meistens nicht. :wink:
