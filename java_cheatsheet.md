 # Java Cheatsheet

# Table of Contents

0. [Tips with IntelliJ](#intellij-tips)
1. [Starting Off](#starting-off)
2. [Types](#types)
3. [Logical Operators](#logical-operators)
4. [Control Flow](#control-flow)
5. [Arrays and ArrayLists](#arrays)
6. [Loops](#loops)
7. [Useful Methods](#useful-methods)
8. [Object Oriented Programming](#object-oriented-programming)
9. [Testing](#testing)
10. [TDD with FizzBuzz](#tdd-test-driven-development)

## ***IntelliJ Tips***

|Command|Description|
|----|-----|
|`cmd + <- or ->`|move to the start or end of the line|
|`fn + backspace`|foward delete|
|`[highlight text] + [ or ( or "`|encompasses text in brackets or quotes|

## ***Starting Off***

**Shortcut:** main + ->|

```java
public class Main {
  public static void main(String[] args) {

  }
}
```

**Class name has to match file name.**

Every line of code that runs in Java must be inside a **class**.

Every program must contain `main()`.


### ***Printing***

**Shortcut:**  sout + ->|

```java
System.out.println("Hello World");
```

`println()` inserts a new line at the end of the output unlike `print()`

```java
String someText = "Hello world";
System.out.println(someText.toUpperCase());
System.out.println(someText.length());
System.out.println(someText.indexOf("world")); //first instance including spaces
```

These are methods.

### ***Commenting***

**Shortcut:** Highlight text -> `cmd + /`

```java
// Single line comment

/* Multiline comment
which spans
multiple lines */
```

### ***Types***

|Type|Description|
|---|---|
|int|integer|
|String|stores text|
|float|32 bit storage of decimals|
|double|64 bit storage of decimals|
|char| single characters surrounded by **single quotes**|
|boolean| `true` or `false`|

e.g. declaration of variable:

**CAMEL CASE!!**

`float myFloat = 5.28f   //remember the f`

`double number = 5.123451d //remember the d`

`String name = "Kevin";`

### ***Primitive Data Types***

Stored in memory with an associated value. Primitive types always start with lower case letter.

Reference types (non-primitive) 

|Type|Size|Description|
|---|----|----|
|`byte`|1 byte|whole numbers from -128 to 127|
|`short`|2 bytes|whole numbers from -32768 to 32767|
|`int`|4 bytes|whole numbers from -2,147,483,648 to 2,147,483,647|
|`long`|8 bytes|whole numbers around +-9e18|
|`float`|4 bytes|sufficient for 6 to 7 decimal digits|
|`double`|8 bytes| 15 decimal digits|
|`boolean`|1 bit| true or false|
|`char`|2 bytes|single character, letter or ASCII value e.g. `(char) 65` gives A|

Large numbers can be represented with e or E for powers of 10,

e.g. `float f1 = 35e6f`

**Converting Types**

|Method|Syntax|
|---|----|
|number to String|`String.valueOf([int/double/float])`|

### ***Logical Operators***
|Operator|Description|
|---|---|
|`&&`|and|
|`[double pipe]`|or|
|`!`|not|

**Should not** use logical operators for non-primitive types,

`"cat".equals("cat")` rather than `"cat" == "cat"`

### ***Control Flow***

**IF**

```java
if(condition){ clause }
else if { clause }
else { clause }
```

```java
String favouriteChocolate = "Bounty";
String result = favouriteChocolate.equals("Bounty") ? "Gross" : "Yum";
System.out.println(result);
```

Can use logical operators with shortened IF statement,

```java
String results = labHandedIn && studentPresent ? "Great" : "Bad";
System.out.println(results);
```

can extend the loop for else if by putting statement after :, e.g. `String results = labHandedIn && studentPresent ? "Great" : labHandedIn || studentPresent ? "Bad" : "No Clue";`

### ***Arrays***

Arrays are harder to resize than arraylists

```java
String[] names = new String[4] //defines an empty array of length 4, new calls constructor
String[] trainers = {"Colin","Zsolt","Ed"};
int[][] myNumbers = { {1,2,3} , {4,5,6} };
```
Accessing the values of the array is the same as Python, e.g. `trainers[0]`

|Method|Syntax|
|---|---|
|Length of the array|`myArray.length`|

### ***ArrayList***

ArrayList is a resizable array that can be found in `java.util` package

**Shortcut**: click on `ArrayList<[type]>` and then, [option + enter] to import class

```java
import java.util.ArrayList; //set before public class

ArrayList<[type]> cars = new ArrayList<>();
```

|Method|Syntax|Extra|
|---|---|--|
|Add elements|`myArrayList.add()`| [cmd + d] to copy selected line, can add `([index],value)` to inset into specific place
|Accessing elements|`~ .get([index])`|
|Changing elements|`~ .set([index], value)`|
|Remove an element from index or first value|`~ .remove([index] or value)`|
|Clear entire list|`~ .clear()`|
|Find the size|`~ .size()`|
|Find index of element|`~ .indexOf(value)`|
|Find if list contains|`~ .contains(value)`|

**Initialising ArrayList with Collections**

```java
import java.util.Collections;

ArrayList<Integer> numbers = new ArrayList<>();
Collections.addAll(numbers, 1, 1, 4, 2, 7, 1, 6, 15, 13, 99, 7);
```

**Sorting ArrayList**

```java
Collections.sort(myArrayList);  //sorts alphabetically or numerically, DESTRUCTIVE METHOD
Collections.sort(myArrayList, Collections.reverseOrder())  //reverse order
```

**Common maths**

```java
Collections.max(myArrayList);
Collections.min(myArrayList);
```

### ***Loops***

**Shortcut:** `fori` + ->|

```java
for(int i = 0 ; i < n ; i++ ) { //loops over a number until i<n, 
  clause                        // can start at different index or 
  }                             // increment differently, CLASSIC

for(int i : n) { //same as for i in n, FOR EACH SYNTAX, "syntactic sugar" = same as above
  clause 
  } 
```
**Break and Continue**

Break stops the for loop from running, therefore if silver is the second element, only the first element is printed

Continue instead, skips over silver and continues the for loop

```java
for (int i = 0 ; i<colours.size(); i++ ){
            if (colours.get(i).equals("silver")){
                break/continue;
            }
            System.out.println(colours.get(i));
        }
```

### ***Useful Methods***

**String**

|Method|Syntax|Extra|
|---|---|---|
|Find value of character| `String.charAt([index])`| finds the character at index of string e.g. beginning character|
|Upper and lowercase| `~ .toUpperCase() / .toLowerCase()`|

### ***Object Oriented Programming***

*Name of class must begin with capital letter and match file name !!*

**Unified Modelling Language (UML) - Class diagrams**

|Person||
|-------|-
|**Properties** |
|- name : String|
|- town : String|
|- completedCourse : boolean|
|**Behaviour** *(same as methods)*|
|+ greet(String) : String|
|+ finishCourse() : void|

`-` is for private, `+` is for public

**Creating a class constructor, properties and behaviours in class Person.java**

```java
public class Person {

    //PROPERTIES

    String name;
    String town;
    boolean completedCourse;

    //CONSTRUCTOR

    public Person(String inputName, String inputTown){ // <----- this is the constructor 
        this.name = inputName;                         // that is called when an object 
        this.town = inputTown;                         // of a class is created
        this.completedCourse = false; //sets every new person's to false
    }

    public ShoppingTrolley(){
        this.shopping = new ArrayList<>();  // this constructs an empty arraylist
    }

    //BEHAVIOURS

    String greet(String timeOfDay){
        return("Good " + timeOfDay + " "+ this.name + "!");
    }

    void finishCourse(){
        this.completedCourse = true;
    }
}
```
Person is now a valid data type that can be used to create new array list e.g. `ArrayList<Person> people = new ArrayList<>();`

**Creating objects and calling behaviours in Runner.java**
```java
public class Runner {

    public static void main(String[] args) {

        Person person = new Person("Kevin","London");  //creates object by calling the 
        Person person2 = new Person("Sandra","Morelia");  //constructor in Person.java
        
        String personGreeting = person.greet("morning");
        String person2Greeting = person2.greet("evening");

        System.out.println(personGreeting);
        System.out.println(person2Greeting);   

        person.finishCourse();
    }
}
```

**ArrayList with new type of data**

```java
        ArrayList<Person> people = new ArrayList<>();
        people.add(person);
        people.add(person2);

        for (Person human : people) {
            System.out.println(human.name +" "+ human.town +" "+ human.completedCourse);
        }
```

|Method|Syntax|Extra|
|----|----|-----|
|Calling properties|`object.property`| e.g. `person.name`, `person2.town`|

**Private properties *(getters and setters)***

In general, properties are private, behaviours are public

```java
        private String name;

        public String getName(){   // GETTERS
            return this.name;
        }

        public void setName(String updatedName){    // SETTERS
            this.name = updatedName;
        }
```
### ***Testing***

.xml is a markup language soon to be taken over by json

**Setting up testing in pom.xml**

Include dependencies below the properties and if red, Maven tab on the side to reload Maven project
```xml
    <dependencies>
        <dependency>
            <groupId>org.junit.jupiter</groupId>
            <artifactId>junit-jupiter-api</artifactId>
            <version>5.8.2</version>
            <scope>test</scope>
        </dependency>

        <dependency>
            <groupId>org.assertj</groupId>
            <artifactId>assertj-core</artifactId>
            <version>3.22.0</version>
            <scope>test</scope>
        </dependency>
    </dependencies>
```
Tests are put into the **GREEN** folder under src/tests/java as a new class

**Import classes junit and assert**

```java
import org.junit.jupiter.api.Test;
import static org.assertj.core.api.AssertionsForClassTypes.assertThat;
```

**Initialising tests**
```java
public class MainTest {

    @Test                        //ANNOTATIONS - put above a method to have 
    public void myFirstTest(){   // some special behaviour to exhibit
        // ENTER TESTS HERE
    }
}
```

**Assertions**

```java
        // BDD -behaviour driven development

        //Given... (Arrange)
        String input = "HElLo";
        //When... (Act)
        String actual = input.toLowerCase();
        //Then... (Assert)
        String expected = "hello";
        assertThat(actual).isEqualTo(expected);
```

**Calculator example**

*Calculator.java*

```java
public class Calculator {

    public int add(int number1, int number2){
        return number1 + number2;
    }

    public int subtract(int number1, int number2){
        return number1 - number2;
    }
}

```

*CalculatorTest.java*

```java
import org.junit.jupiter.api.BeforeEach;
import org.junit.jupiter.api.Test;
import static org.assertj.core.api.AssertionsForClassTypes.assertThat;

public class CalculatorTest {

    private Calculator calculator;

    @BeforeEach
    public void setUp(){     // Sets up before each test
        calculator = new Calculator();
    }

    @Test
    public void canAddNumbers(){
        //Given
        // This is set outside the tests under @BeforeEach
        //When
        int actual = calculator.add(4,9);
        //Then
        int expected = 13;
        assertThat(actual).isEqualTo(expected);
    }

    @Test
    public void canSubtractNumbers(){

        int actual = calculator.subtract(2,7);
        int expected = -5;
        assertThat(actual).isEqualTo(expected);
    }

}
```

### **TDD (Test Driven Development)**

1. Plan criteria for the code to pass
2. Write tests for the code
3. Write code that passes the tests

E.g. FizzBuzz problem :

- any number divisible by 3 should give back fizz
- any number divisible by 5 should give back buzz
- any number divisible by both should give back fizzbuzz
- any number not divisible by either should give back the number itself

FizzBuzzTest.java

```java
import org.junit.jupiter.api.BeforeEach;
import org.junit.jupiter.api.Test;

import static org.assertj.core.api.AssertionsForClassTypes.assertThat;

public class FizzBuzzTest {

    private FizzBuzz fizzBuzz;

    @BeforeEach
    public void setUp(){
        fizzBuzz = new FizzBuzz();
    }

    @Test
    public void canReturnFizz(){
        //Given
        //When
        String result = fizzBuzz.getFizzBuzz(3);
        //Then
        String expected = "Fizz";
        assertThat(result).isEqualTo(expected);
    }

    @Test
    public void canReturnBuzz(){
        String result = fizzBuzz.getFizzBuzz(5);
        String expected = "Buzz";
        assertThat(result).isEqualTo(expected);
    }

    @Test
    public void canReturnFizzBuzz(){
        String result = fizzBuzz.getFizzBuzz(15);
        String expected = "FizzBuzz";
        assertThat(result).isEqualTo(expected);
    }

    @Test
    public void canReturnNumberAsString(){
        String result = fizzBuzz.getFizzBuzz(17);
        String expected = "17";
        assertThat(result).isEqualTo(expected);
    }

}
```

FizzBuzz.java

```java
public class FizzBuzz {

    public String getFizzBuzz(int number){
        if(number %3 == 0 && number %5 == 0){
            return "FizzBuzz";
        }

        if (number %3 == 0){
            return "Fizz";
        }

        if (number %5 == 0){
            return "Buzz";
        }
        return String.valueOf(number);
    }
}
```
Run FizzBuzz test with coverage by right clicking the test

[Back to Top](#java-cheatsheet)