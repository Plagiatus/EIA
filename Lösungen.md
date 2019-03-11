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
