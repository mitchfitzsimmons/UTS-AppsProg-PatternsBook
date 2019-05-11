# Apps Prog Patterns Book
-
This is the patterns book for applications programming
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
* Output
* Read
* Read Loop
* Array Loop
* Count

<br>
-
-
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
-
<br>


####The output pattern
Goal: Show a value to the user.

* **Pattern:** ```System.out.println(“<label>” + <value>);```
* **e.g. show an age:** ``` System.out.println(“age is “ + age);```
* **e.g. show a name:** ```System.out.println(“name is “ + name);```
 
<br>
-
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
-
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
-
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
-
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
-
<br>


### Methods

### Classes

### Lists 