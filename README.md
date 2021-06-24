
Big O Personnel Learning

<img width="600" height="350" alt="bigocomplexitychart" src="https://user-images.githubusercontent.com/27411868/114745216-163c2000-9d6c-11eb-884a-1c1e9071ef03.PNG">

## Big Os-
* O(1) Constant- no loops

```javascript
        if (a === b) {
        	console.log('a equals to b');
        }
```

* O(log N) Logarithmic- usually searching algorithms have log n if they are sorted (Binary Search)
* O(n) Linear- for loops, while loops through n items
 
```javascript
        var array = [1,2,3,4,5,6]; // O(1)
	functionFindEven(arr){ // O(1)
		for (let i =0; i < arr.length; i++) {
			if(arr[i]%2 === 0) { // O(N)
				console.log(arr[i]); // O(N)
			}
		}
	}
	functionFindEven(array); // O(1)
	
	// worst is O(N), so its complexity is O(N). 
	// This type of complexity increase as the numbers of elements in array increases, so it is LINEAR TIME.
```
* O(n log(n)) Log Liniear- usually sorting operations
* O(n^2) Quadratic- every element in a collection needs to be compared to each other element. Two nested loops
* O(2^n) Exponential- recursive algorithms that solves a problem of size N
* O(n!) Factorial- you are adding a loop for every element

### Iterating through half a collection is still O(n)

### What can cause time in a function?-
    * Operations (+, -, *, /)
    * Comparisons (<, >, ==)
    * Looping (for, while)
    * Outside Function call (function())

## Rule Book-
* Rule 1: Always worst Case, so if a program has multiple is processing only half an array we still consider the worst case as Big O of O(N).
* Rule 2: Remove Constants, if a program has constant like 2, 100 etc remove them. And also the division ones for example:

```javascript
        var array = [1,2,3,4,5,6]; // O(1)
	printHalfArray(arr){ // O(1)
		var middleIndex = Math.floor(arr.length/2);
		for(let i = 0; i < 100; i++) { // O(100)
			conslole.log(i);
		}
		for (let i =0; i < middleIndex; i++) {
			console.log(arr[i]); // O(N/2)
		}
	}
	printHalfArray(array); // O(1)
	
	// worst is O(N/2 + 100), but when the number N is very large then dividing by 2 and adding 100, doenst matter and in Big O we consider only large numbers of value N. 
	// So final Big O is O(N)
	
	// simillarly let say there are two loops processing N data, in that case Big O should be (2n) but with the Rule 2 this become Big O of O(n)
```
* Rule 3: Different inputs should have different variables. O(a+b). A and B arrays nested would be
  * O(a + b)   ○ + for steps in order
```javascript
        var array = [1,2,3,4,5,6]; // O(1)
	var array2 = [1,2,3,4,5,6]; // O(1)
	printTwoArray(arr1, arr2){ // O(1)
		for (let i =0; i < arr1.length; i++) {
			console.log(arr1[i]); // O(a) length of array 1
		}
		for (let i =0; i < arr2.length; i++) {
			console.log(arr2[i]); // O(b) length of array 2
		}
	}
	printTwoArray(array, array2); // O(1)
	
	// Big O of this is O(a + b)
	
	// Now suppose it is processing on only one array and there are two for loops on same array steps by steps not nested
	// it will become O(n + n) => O(2n)
	// But as per rule 2 remove constant it will finalyy become O(N)
```

  * O(a * b)     ○ * for nested steps

```javascript
        var array = [1,2,3,4,5,6]; // O(1)
	var array2 = [1,2,3,4,5,6]; // O(1)
	printTwoArrayNested(arr1, arr2){ // O(1)
		for (let i =0; i < arr1.length; i++) {
			console.log(arr1[i]); // O(a) length of array 1
			for (let i =0; i < arr2.length; i++) {
				console.log(arr2[i]); // O(b) length of array 2
			}
		}
	}
	printArrayTwice(array, array2); // O(1)
	
	// Big O of this is O(a * b)
	
	// Now suppose it is processing on only one array and there are two for loops on same array and are nested
	// it will become O(n * n) => O(n ^ 2) n square
```

* Rule 4: Drop Non-dominant terms

```javascript
        var array = [1,2,3,4,5,6]; // O(1)
	printTwoArrayNested(arr1){ // O(1)
		for (let i =0; i < arr1.length; i++) { // O(N)
			console.log(arr1[i]); 
		}
		for (let i =0; i < arr1.length; i++) {  //O(N^2)
			console.log(arr1[i]);
			for (let i =0; i < arr1.length; i++) {
				console.log(arr1[i]); 
			}
		}
	}
	printArrayTwice(array); // O(1)
	
	// Big O of this is O(n + n^2), now when n is very large n^2 will bemoce very large and adding n will not make any difefrences,
	// so here the dominent term is on N^2
	// so finalyy it will be Big O of O(n^2)
```

## Cheat Sheat
* O(1) Constants no loops
* O(log n) Logarithmic usually searching algos
* O(n) linear for, while loops etc
* O(n * log(n)) Log Linear Sorting Operations usually
* O (n^2) Quadratic, Nested Loops, every collection needs to be comapared to every element.
* O(2^n) Exponential, recursive algo that solve a problem of size N
* O(n!) you are adding a loop for every element.

## What causes Space complexity?-
* Variables
* Data Structures
* Function Call
* Allocations


