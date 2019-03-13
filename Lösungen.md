# Lösungen

_Die Lösungen sind noch in Arbeit und kommen hoffentlich nach und nach._

### :information_source: Die hier angegebenen Lösungen sind nur _eine_ von vielen.
Programmieren ist ein kreativer Prozess mit mehr als einer Lösung. Wir versuchen selbstverständlich euch die einfachste und am besten verständliche Lösung zu präsentieren, aber das gelingt meistens nicht. :wink:


**Falls es Unklarheiten oder Fragen gibt, zögert nicht mich darauf anzusprechen, am besten über die [Issues](https://github.com/Plagiatus/EIA/issues).**

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

## Aufgabe 4
### 4.1
Bekannt sollten sein: Boolean, Number, String(, Any). Aber es gibt noch mehr: [Klicke hier falls es interessiert, diese Typen sind für uns aber größtenteils erstmal nicht relevant](https://www.typescriptlang.org/docs/handbook/basic-types.html) _(besonders der Hinweis ganz am Ende der Seite ist noch interessant)_.

### 4.2
interface oder class. Der Vollständigkeit halber soll hier noch object genannt werden, ist aber für uns nicht relevant.

### 4.3

```typescript
interface Student{
	name: string;
	matrikel: number;
	studiengang: string;
}

let s1: Student = {name: "Max Mustermann", matrikel: 123456, studiengang: "MIB"};
let s2: Student = {name: "Monika Musterfrau", matrikel: 654321, studiengang: "WNB"};
let s3: Student = {name: "Thomas Teufel", matrikel: 666666, studiengang: "SSB"};

let studenten: Student[] = [s1, s2, s3];
console.log(studenten[0].name);

function showInfo(s: Student): void {
	console.log(`${s.name}, Matrikelnummer ${s.matrikel}, Studiengang ${s.studiengang}`);
}
showInfo(studenten[0]);
showInfo(studenten[1]);
showInfo(studenten[2]);
```

---

### :information_source: Die hier angegebenen Lösungen sind nur _eine_ von vielen.
Programmieren ist ein kreativer Prozess mit mehr als einer Lösung. Wir versuchen selbstverständlich euch die einfachste und am besten verständliche Lösung zu präsentieren, aber das gelingt meistens nicht. :wink:

## Aufgabe 5
### 5.1
```typescript
function add(a: number, b: number): number {
	return a + b;
}
```

### 5.2
```typescript
function divideable(a: number, b:number): boolean {
	return a % b == 0;
}
```

### 5.3
```typescript
function ggT(a: number, b:number): number{
	if(a == 0) return b;
	if(b == 0) return a;
	
	let tmp: number;
	while (b != 0){
		tmp = a % b;
		a = b;
		b = tmp;
	}
	return a;
}

console.log(ggT(3528,3780)); 	//252
```
Es gibt viele Möglichkeiten einen größten gemeinsamen Teiler zu berechnen, ich nutze hier einen modernen euklidischen bzw steinischen Algorithmus.

Ein Brute-Force Ansatz wäre natürlich auch denkbar: Nehme die kleinere der beiden Zahlen und prüfe ob bei der Division mit beide Zahlen kein Rest bleibt. Wiederhole solange mit der zahl--, bis dies der Fall ist. Das ist natürlich absolut unoptimiert und hat eine lange Laufzeit, aber so wäre es definitv möglich. Codebeispiel (nur für positive Zahlen):  

```typescript
function ggT(a: number, b:number): number{
	//angenommen dass b kleiner ist als a
	let tmp: number = b;
	while (a % tmp != 0 || b % tmp != 0) {
		tmp--;
	}
	return tmp;
}
```

### 5.4
```typescript
function kgV(a: number, b: number): number{
	//berechnung über den ggT
	return (a / ggT(a, b)) * b;
}
```
Der kgV und der ggT hängen direkt zusammen (von Wikipedia): ![bild](https://wikimedia.org/api/rest_v1/media/math/render/svg/97031de120e42d752c1d5cdcaaf2fcf487d639bd).  
 Wir können diese Formel also umformen um den kgV zu berechnen. Auch hier sind natürlich andere Ansätze Möglich (Primfaktorzerlegung) aber wenn wir bereits den ggT haben, ist dieser Ansatz am einfachsten.
 
 ### 5.5
 #### 5.5.1
 ```typescript
 function summeBisN(n: number): number{
	let sum: number = 0;
	for(let i: number = 0; i < n; i++){
		sum += (1 / Math.pow(2, i + 1));
	}
	return sum;
}
console.log(summeBisN(20)); 	// 0.9999990463256836
 ```
 
 #### 5.5.2
 ```typescript
 function summeBisEpsilon(epsilon: number): number{
	let sum: number = 0;
	let summand: number = 0.5;
	while(summand >= epsilon){
		sum += summand;
		summand /= 2;
	}
	return sum;
}
console.log(summeBisEpsilon(0.001)); 	// 0.998046875
 ```
 
 ---

### :information_source: Die hier angegebenen Lösungen sind nur _eine_ von vielen.
Programmieren ist ein kreativer Prozess mit mehr als einer Lösung. Wir versuchen selbstverständlich euch die einfachste und am besten verständliche Lösung zu präsentieren, aber das gelingt meistens nicht. :wink:

## Aufgabe 6
### 6.1
```typescript
function backwards(input: number[]): number[]{
	let output: number[] = [];
	for(let i: number = 0; i < input.length; i++){
		output[input.length - i - 1] = input[i];
	}
	return output;
}
```

### 6.2
```typescript
function join(input1: number[], input2: number[]): number[]{
	let output: number[] = [];
	let i: number;
	for(i = 0; i < input1.length; i++){
		output[i] = input1[i];
	}
	for(let a: number = 0; a < input2.length; a++){
		output[a+i] = input2[a];
	}
	return output;
}
```

### 6.3 
```typescript
function split(input: number[], firstIndex: number, lastIndex: number): number[]{
	//either of them is negative
	if(firstIndex < 0 || lastIndex < 0) return null;
	//start is bigger than end
	if(firstIndex > lastIndex) return null;
	//either of the indexes is out of the scope of the input array
	if(firstIndex > input.length - 1 || lastIndex > input.length - 1) return null;

	let output: number[] = [];
	for(let i: number = 0; i < lastIndex - firstIndex + 1; i++){
		output[i] = input[firstIndex + i];
	}
	return output;
}
```

### 6.4
```typescript
function sort(input: number[]): number[]{
	let output: number[] = [];

	//kopiere input in output, s. call by reference
	for(let a: number = 0; a < input.length; a++){
		output[a] = input[a];
	}

	//rudimentärer sortieralgorithmus
	for(let n: number = 0; n < output.length; n++){
		for(let i: number = 0; i < output.length - 1; i++){
			if(output[i] > output[i + 1]){
				let tmp = output[i];
				output[i] = output[i+1];
				output[i+1] = tmp;
			}
		}
	}

	return output;
}
```
Sehr rudimentärer und unoptimierter Sortieralgorithmus: Gehe Schritt für Schritt alle Objekte des Arrays durch. Wenn sie größer sind als das Nachfolge-Element, vertausche sie. Gehe das Array so oft komplett durch, wie Elemente im Array sind, dadurch ist sichergestellt, dass alle Positionen sortiert sind. Eine schlechte Form des [Bubblesort](https://de.wikipedia.org/wiki/Bubblesort).

Mit Richtungsänderung:

```typescript
function sort(input: number[], ascending: boolean = true): number[]{
	let output: number[] = [];

	//kopiere input in output, s. call by reference
	for(let a: number = 0; a < input.length; a++){
		output[a] = input[a];
	}

	//rudimentärer sortieralgorithmus
	for(let n: number = 0; n < output.length; n++){
		for(let i: number = 0; i < output.length - 1; i++){
			if(ascending){
				if(output[i] > output[i + 1]){
					let tmp = output[i];
					output[i] = output[i+1];
					output[i+1] = tmp;
				}
			} else {
				if(output[i] < output[i + 1]){
					let tmp = output[i];
					output[i] = output[i+1];
					output[i+1] = tmp;
				}
			}
		}
	}

	return output;
}
```
Auch hier wieder sehr rudimentär und nicht sehr schön aber hoffentlich nachvollziehbar. Schöner wäre es eine Lösung zu finden, bei der der vertauschen Algorithmus nicht kopiert werden muss. Denn merke: Wenn man Code einfach nur kopiert ohne daran etwas zu ändern, macht man etwas falsch.

### 6.5 
Keine Lösung nötig

---

### :information_source: Die hier angegebenen Lösungen sind nur _eine_ von vielen.
Programmieren ist ein kreativer Prozess mit mehr als einer Lösung. Wir versuchen selbstverständlich euch die einfachste und am besten verständliche Lösung zu präsentieren, aber das gelingt meistens nicht. :wink:

## Aufgabe 7
### 7.1
```typescript
let stack: number[] = []

function insert(a: number): void{
	stack[stack.length] = a;
}

function take(): number{
	if(stack.length == 0) return null;
	let tmp: number = stack[stack.length - 1];
	stack.splice(stack.length - 1);
	return tmp;
}
```

#### 7.1.1
```typescript
function insert(a: number): void{
	if(stack.length >= 10) return;
	stack[stack.length] = a;
}
```

### 7.2
```typescript
let primes: number[] = [2];

let numToTest: number = 3;
let isPrim: boolean;
while(primes.length < 1000){
	isPrim = true;
	for(let i: number = 0; i < primes.length && isPrim; i++){
		if(numToTest % primes[i] == 0){
			isPrim = false;
		}
	}
	if(isPrim) {
		primes.push(numToTest);
	}
	numToTest++;
}
console.log(primes[999]);
```
Die 1000ste Primzahl ist 7919. Wer weitere seiner Primzahlen prüfen möchte, [klickt hier](https://primes.utm.edu/nthprime/index.php#nth).

### 7.3
#### 7.3.1
```typescript
function amountVocals(input: string){
	let a: number = 0;
	let e: number = 0;
	let i: number = 0;
	let o: number = 0;
	let u: number = 0;

	for(let x: number = 0; x < input.length; x++){
		switch(input[x]){
			case "a":
			case "A":
				a++;
				break;
			case "e":
			case "E":
				e++;
				break;
			case "i":
			case "I":
				i++;
				break;
			case "o":
			case "O":
				o++;
				break;
			case "u":
			case "U":
				u++;
				break;
			default:
				//do nothing
				break;
		}
	}
	console.log(`The input string "${input}" has ${a} a's, ${e} e's, ${i} i's, ${o} o's and ${u} u's.`);
}
```
Hier sind selbstverständlich auch kompaktere Lösungen denkbar, aber dies ist eine übersichtliche und verständliche Lösung.

#### 7.3.2
```typescript
function toLowerCase(input: string): string{
	let output: string = "";
	let magicNumber: number = "a".charCodeAt(0) - "A".charCodeAt(0);	//32
	for(let i: number = 0; i < input.length; i++){
		if(input.charCodeAt(i) >= "A".charCodeAt(0) && input.charCodeAt(i) <= "Z".charCodeAt(0)){
			output += String.fromCharCode(input.charCodeAt(i) + magicNumber);
		} else {
			output += input.charAt(i);
		}
	}
	return output;
}
```

#### 7.3.3
```typescript
unction encrypt(input: string): string {
	let output: string = "";
	for (let i: number = 0; i < input.length; i++) {
		//Großbuchstabe
		if ((input.charCodeAt(i) >= "A".charCodeAt(0) && input.charCodeAt(i) < "Z".charCodeAt(0)) ||
			(input.charCodeAt(i) >= "a".charCodeAt(0) && input.charCodeAt(i) < "z".charCodeAt(0))) {
			output += String.fromCharCode(input.charCodeAt(i) + 1);
		//Kleinbuchstabe
		} else if (input[i] == "z" || input[i] == "Z") {
			output += String.fromCharCode(input.charCodeAt(i) - 25);
		//Alles andere
		} else {
			output += input[i];
		}
	}
	console.log("encrypted string:", output);
	return output;
}
```

#### 7.3.4
```typescript
function decrypt(input: string): string {
	let output: string = "";
	for (let i: number = 0; i < input.length; i++) {
		if ((input.charCodeAt(i) > "A".charCodeAt(0) && input.charCodeAt(i) <= "Z".charCodeAt(0)) ||
			(input.charCodeAt(i) > "a".charCodeAt(0) && input.charCodeAt(i) <= "z".charCodeAt(0))) {
			output += String.fromCharCode(input.charCodeAt(i) - 1);
		} else if (input[i] == "a" || input[i] == "A") {
			output += String.fromCharCode(input.charCodeAt(i) + 25);
		} else {
			output += input[i];
		}
	}
	console.log("decrypted string:", output);
	return output;
}
```

#### 7.3.5
```typescript
function encrypt(input: string, n: number = 1): string {
	let output: string = "";
	for (let i: number = 0; i < input.length; i++) {
		if (input.charCodeAt(i) >= "A".charCodeAt(0) && input.charCodeAt(i) <= "Z".charCodeAt(0)){
			output += String.fromCharCode( (input.charCodeAt(i) - "A".charCodeAt(0) + n) % 26 + "A".charCodeAt(0));
		} else if (input.charCodeAt(i) >= "a".charCodeAt(0) && input.charCodeAt(i) <= "z".charCodeAt(0)){
			output += String.fromCharCode( (input.charCodeAt(i) - "a".charCodeAt(0) + n) % 26 + "a".charCodeAt(0));
		} else {
			output += input[i];
		}
	}
	console.log("encrypted string:", output);
	return output;
}

function decrypt(input: string, n: number = 1): string {
	let output: string = "";
	for (let i: number = 0; i < input.length; i++) {
		if (input.charCodeAt(i) >= "A".charCodeAt(0) && input.charCodeAt(i) <= "Z".charCodeAt(0)){
			output += String.fromCharCode( (26 + (input.charCodeAt(i) - "A".charCodeAt(0) - n)) % 26 + "A".charCodeAt(0));
		} else if (input.charCodeAt(i) >= "a".charCodeAt(0) && input.charCodeAt(i) <= "z".charCodeAt(0)){
			output += String.fromCharCode( (26 +(input.charCodeAt(i) - "a".charCodeAt(0) - n)) % 26 + "a".charCodeAt(0));
		} else {
			output += input[i];
		}
	}
	console.log("decrypted string:", output);
	return output;
}
```
Anmerkung zum Entschlüsseln: Je nach dem ob die Rechnung -1 % 26 das Ergebnis -1 oder 25 hat, braucht man die hinzugefügte `26 +`. TS sagt -1 mod 26 ist -1, darum wird es benötigt.

### 7.4
```typescript
function recursiveFaculty(n: number): number{
	if (n <= 0) return 1;
	return n * recursiveFaculty(n-1);
}
```
Wenn man auch negative Zahlen zulassen möchte, so wäre eine einfache Änderung diese hier:

```typescript
function recursiveFaculty(n: number): number{
	if (n == 0) return 1;
	return n * recursiveFaculty(n - Math.sign(n));
}
```
[Math.sign](https://developer.mozilla.org/de/docs/Web/JavaScript/Reference/Global_Objects/Math/sign)(Benötigt Buildtarget ES2015, ES6 oder neuer)

### 7.5
```typescript
function recursiveFibbonacci(n: number): number{
	if (n <= 0) return 0;
	if (n == 1) return 1;
	return recursiveFibbonacci(n-1) + recursiveFibbonacci(n-2);
}
```

---

### :information_source: Die hier angegebenen Lösungen sind nur _eine_ von vielen.
Programmieren ist ein kreativer Prozess mit mehr als einer Lösung. Wir versuchen selbstverständlich euch die einfachste und am besten verständliche Lösung zu präsentieren, aber das gelingt meistens nicht. :wink:
