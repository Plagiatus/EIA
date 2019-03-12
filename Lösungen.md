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

---

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

---

### :information_source: Die hier angegebenen Lösungen sind nur _eine_ von vielen.
Programmieren ist ein kreativer Prozess mit mehr als einer Lösung. Wir versuchen selbstverständlich euch die einfachste und am besten verständliche Lösung zu präsentieren, aber das gelingt meistens nicht. :wink:

## Aufgabe 3
### 3.1
```typescript
let a: boolean = true;
let b: boolean = true;
let c: boolean = false;

let erg: boolean = ((!a || b) && c) || ((!b || c) && a);
console.log(erg);			//false
```

### 3.2
```typescript
let erg: number = 0;
let i: number = 1;
while (i <= 100){
	erg += i;
	i++;
}
console.log(erg);       //5050
```

### 3.3
```typescript
let erg: number = 1;
let i: number = 1;
do {
	erg = erg * i;
	i++;
} while (i <= 8)
console.log(erg);       //40320
```

### 3.4 
```typescript
let num1: number = 0;
let num2: number = 1;
console.log(num1);
console.log(num2);
for(let i: number = 1; i < 20; i++){
	let tmp: number = num2 + num1;
	num1 = num2;
	num2 = tmp;
	console.log(num2);
}
```
20. Fibonacci Zahl: 6765

### 3.5
```typescript
for(let i: number = 0; i < 10; i++){
	let num: number = Math.floor(Math.random() * 2147483647)
	console.log(num);
}
```
_Ich habe 2147483647 genutzt weil das genau 2<sup>31</sup>-1 entspricht, was in vielen Sprachen das obere Limit für Ganzzahlwerte in 32 bit Systemen ist, und auch das nur um euch ganz nebenbei diesen Fakt beizubringen._

### 3.6
```typescript
function prim(min: number, max: number): void {
	for (let i: number = min; i < max; i++) {   //für jede Zahl i zwischen dem Minimum und Maximum
		let isPrim: boolean = true;			    //gehe davon aus, dass die Zahl i prim ist
		for (let a: number = 2; a < i; a++) {   //für jede Zahl a zwischen 2 und der zu prüfenden Zahl i
			if (i % a == 0) {                   //wenn die Zahl i durch a teilbar ist, ist sie keine Primzahl
				isPrim = false;
			}
		}
		if (isPrim) {                           //nachdem alle Zahlen getestet wurden, ist es immernoch prim?
			console.log(i);								
		}
	}
}

prim(1, 100);                                   //zum testen
```

### 3.7
```typescript
for (let i: number = 1900; i < 2019; i++) {
    let istSchaltjahr: boolean = false;
    if (i % 4 == 0) {
        if (i % 100 == 0) {
            if (i % 400 == 0){
                istSchaltjahr = true;
            }
        } else {
            istSchaltjahr = true;
        }
    }
    if(istSchaltjahr){
        console.log(i);
    }
}
```
kürzer, aber unübersichtlicher:
```typescript
for (let i: number = 1900; i < 2019; i++) {
    if (i % 4 == 0 && (!(i % 100 == 0)) || i % 400 == 0) {
        console.log(i);
    }
}
```

### 3.8 
```typescript
for(let huehner:number = 0; huehner <= 45; huehner++){
	for(let schafe: number = 0; schafe <= 22; schafe++){
		if(gesamtBeine(huehner, schafe) == 90){
			console.log(`${huehner} Hühner, ${huehner * 2} Gänse, ${schafe} Schafe, ${schafe * 3} Kaninchen`)
		}
	}
}

function gesamtBeine(huehnerGesamt: number, schafeGesamt: number): number {
	let huhnerBeine: number = huehnerGesamt * 2;
	let gaenseBeine: number = huehnerGesamt * 2 * 2;
	let schafeBeine: number = schafeGesamt * 4;
	let kaninchenBeine: number = schafeGesamt * 3 * 4;

	return huhnerBeine + gaenseBeine + schafeBeine + kaninchenBeine;
}
```
Ergebnisse:
7 Hühner, 14 Gänse, 3 Schafe, 9 Kaninchen
15 Hühner, 30 Gänse, 0 Schafe, 0 Kaninchen

Beide Ergebnisse gefunden?

### 3.9
```typescript
function rueckgeld(preis: number, gegeben: number): void {
	if(gegeben < preis){
		console.log("Zu wenig Geld gegeben");
		return;
	}
	let zurueck: number = gegeben - preis;
	let geld: number[] = [500,200,100,50,20,10,5,2,1,0.5,0.2,0.1,0.05,0.02,0.01];
	let geldzurueck: number[] = [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0];
	for(let i: number = 0; i < geld.length; i++){
		while(zurueck > geld[i]){
			geldzurueck[i]++;
			zurueck -= geld[i];
		}
	}
	console.log(`Scheine: ${geldzurueck[0]} 500er, ${geldzurueck[1]} 200er, ${geldzurueck[2]} 100er, ${geldzurueck[3]} 50er, ${geldzurueck[4]} 20er, ${geldzurueck[5]} 10er, ${geldzurueck[6]} 5er,
	Münzen: ${geldzurueck[7]} 2er, ${geldzurueck[8]} 1er, ${geldzurueck[9]} 50er, ${geldzurueck[10]} 20er, ${geldzurueck[11]} 10er, ${geldzurueck[12]} 5er, ${geldzurueck[13]} 2er, ${geldzurueck[14]} 1er`);
}

rueckgeld(0.02, 1000);
```
Hier wäre es natürlich auch eine Möglichkeit, jeden Wert einzeln abzufragen und eine eigene Schleife/Abfrage zu schreiben. Durch diese Lösung kann der Code aber auf ein Minimum reduziert werden und wird so nicht nur übersichtlicher sondern auch Wartungsfreundlicher. Die Abfrage am Anfang war nicht gefragt.

---

### :information_source: Die hier angegebenen Lösungen sind nur _eine_ von vielen.
Programmieren ist ein kreativer Prozess mit mehr als einer Lösung. Wir versuchen selbstverständlich euch die einfachste und am besten verständliche Lösung zu präsentieren, aber das gelingt meistens nicht. :wink:

