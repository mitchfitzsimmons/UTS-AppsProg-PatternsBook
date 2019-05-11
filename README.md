# Apps Prog Patterns Book

This is the patterns book for the subject Applications Programming at UTS.
<br/>

## Table of Contents
### Basic Patterns
* Sum
* Output
* Read
* Read Loop
* Array Loop
* Count

### Methods
* String Functions
	* String Loop
	* For-each Loop
	* Looping over words in a string user "split"
	* Split by one or more spaces
	* More String Functions
* Functional Patterns
	* Read loop with read functions
	* Merged read loop
	* The “any” pattern
	* The “every” pattern
	* The “none” pattern


<br>
---
<br>

## Basic Patterns
#### Sum pattern
**Goal:** Find the sum of a collection of items.

```Java
<type> sum = 0;
 <for each item>
 {
     sum += <item>;
 }
```
* Words enclosed between ```<angled brackets>``` are holes that need to be filled.
* ```<type>```  is typically double or int
* ```<for each item>``` is any loop
over a collection of items
* ```<item>``` refers to the next item in
the loop.
* x += y adds the amount y onto x

<br>
---
<br>


####The output pattern
Goal: Show a value to the user.

* **Pattern:** ```System.out.println(“<label>” + <value>);```
* **e.g. show an age:** ``` System.out.println(“age is “ + age);```
* **e.g. show a name:** ```System.out.println(“name is “ + name);```
 
<br>

---

<br>


#### Read Pattern 

Goal: Read a value from the user.


* **Pattern:** 

```Java
System.out.print(“<prompt>”);
<type> <variable> = <read operation>;
```
*or*

```Java
System.out.print(“<prompt>”); 
<variable> = <read operation>;
```
* **e.g. read an age:** 

```Java
System.out.print(“Age: “); int age = In.nextInt();
```

<br>

---

<br>

#### Read Loop Pattern

**Goal:** Read values until the user enters an “end of input” value.

```Java
<read pattern>
while (<value> != <end value>) {
   <use the value>
   <read pattern>
}
```
**Observations:** 

* \<read pattern\> appears twice
* always test for the “end of input”
value immediately after a \<read pattern>.

<br>
---
<br>

#### Array Loop Pattern

**Goal:** Loop over items in an array.

```Java
for (int i = 0; i < <array>.length; i++)
{
   <use the item array[i]>
}
```

<br>

---

<br>

#### Count Pattern

**Goal** (without guard): Count the number of items in a collection. 

```Java
int count = 0;
<for each item>
	count++;
```
**Goal** (with guard): Count the number of items that satisfy a condition.
 
```Java
int count = 0;
<for each item>
	if (<guard>)
		count++;
```
<br>

---

<br>


## Methods
### Strings
#### String Loop
**Goal:** Loop over the characters in a string.

```Java
for (int i = 0; i < <str>.length(); i++) {
   <use character str.charAt(i)>
}
```
**Example:** Count the number of l’s in the word “hello”

```Java
String s = “hello”;
int count = 0;
for (int i = 0; i < s.length(); i++) {
    if (s.charAt(i) == ‘l’)
         count++;
}
System.out.println(“Number of l’s = “ + count);
```

<br>

---

<br>

#### For-each Loop
**Goal:** Loop over items in an array.

Create an array of values

```String[] array = { “car”, “truck”, “bus”, “van” };```

These two code fragments do the same thing: 

**Array Loop**

```Java
for (int i = 0; i < array.length; i++)
System.out.println(array[i]);
```
**For-Each Loop**

```Java
for (String word : array) 
System.out.println(word);
```
<br>
**Read:** For each word in array, print that word.


<br>

---

<br>

#### Looping over words in a string user "split"
**Program**

```Java
String sentence = “Eat your vegetables”;
for (String word : sentence.split(“ “))
   System.out.println(“Next word = “ + word);
```

**Console Output**

```
Next word = Eat
Next word = your
Next word = vegetables
```

<br>

---

<br>

#### Split by one or more spaces
* If you have a string with extra spaces between words:

```Java
String sentence = “Eat your vegetables”;
```

* Use the regular expression “ +” as the separator

```Java
for (String word : sentence.split(“ +“))
   System.out.println(“Next word = “ + word);
```

<br>

---

<br>

#### More String Functions

Function  | What is does
------------- | -------------
```boolean contains(String s)```  | does this string contain s?
```int indexOf(String s)```  | returns the position where s is found
```boolean startsWith(String s)```  | does this string start with s?
```boolean endsWith(String s)```  | does this string end with s?
```boolean equals(String s)```  | does this string equal s?
```String substring(start, end) ```  | returns a substring from start to end
```String toUpperCase()``` / ```String toLowerCase()```  | returns the string in upper/lower case
```String trim()```  | returns the string without leading/trailing spaces.



<br>

---

<br>

### Functional Patterns

#### Read loop with read functions

```Java
int age = readAge(); while (age != -1) {
<use age>
age = readAge(); }
int readAge() {
    System.out.print(“Age: “);
    return In.nextInt();
}

```

**Problem:** There is still repeated code: age = readAge();


<br>

---

<br>

#### Merged read loop

```Java
int age;
while ((age = readAge()) != -1) {
<use age> }
int readAge() {
    System.out.print(“Age: “);
    return In.nextInt();
}
```
***Key:*** call readAge() inside the while condition


##### Whenever you need a read loop, always use the merged read loop.
**Example:** reading characters:

```Java
char c;
while ((c = readChar()) != ‘.’) { <use c>
}
```

* **Example:** reading strings:

```Java
String s;
while (!(s = readString()).equals(“end”)) { <use s>
}
```

<br>

---

<br>

#### The “any” pattern
**Goal:** Determine if any item in a collection passes <test>

```Java
<for each item>
    if (<item passes test>)
         return true;
return false;
```

**Example:** Test if any number in an array is negative:

```
boolean anyNegative(int[] array) {
    for (int item : array)
         if (item < 0)
             return true;
    return false;
```

<br>

---

<br>

#### The “every” pattern
**Goal:** Determine if all items in a collection pass <test>

```Java
<for each item>
    if (! <item passes test>)
         return false;
return true;
```


<br>

---

<br>

#### The “none” pattern
**Goal:** Determine if no items in a collection pass <test>

```Java
<for each item>
    if (<item passes test>)
         return false;
return true;
```


<br>

---

<br>

## Classes

## Lists 