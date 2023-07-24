 # Java Cheatsheet

# Table of Contents

0. [Tips with IntelliJ](#intellij-tips)
1. Week 1 -
    * [Starting Off](#starting-off)
    * [Types](#types)
    * [Logical Operators](#logical-operators)
    * [Control Flow](#control-flow)
    * [Arrays and ArrayLists](#arrays)
2. Week 2 - [Loops](#loops)
    * [Useful Methods](#useful-methods)
    * [Object Oriented Programming](#object-oriented-programming)
    * [Testing](#testing)
    * [TDD with FizzBuzz](#tdd-test-driven-development)
    * [Multiple Classes](#multiple-classes)
3. Week 3 -
    * [Inheritance](#inheritance)
    * [Setting Up Interfaces](#setting-up-interfaces)
    * [Association](#association)
    * [Algorithms and Big O Notation](#algorithms-and-big-o-notation)
    * [Stacks and Queues](#stacks-and-queues)
4. Week 4 - 
    * [ENUM](#enum)
    * [Scanners and Exceptions](#scanners-and-exceptions)
    * [](#)
0. [UML Cheatsheet](#uml-cheatsheet)
    * [](#)


## ***IntelliJ Tips***

|Command|Description|
|----|-----|
|`cmd + <- or ->`|move to the start or end of the line|
|`fn + backspace`|foward delete|
|`[highlight text] + [ or ( or "`|encompasses text in brackets or quotes|
|`cmd + [click]`|can jump from one error to method in another file|

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


### **Printing**

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

### **Commenting**

**Shortcut:** Highlight text -> `cmd + /`

```java
// Single line comment

/* Multiline comment
which spans
multiple lines */
```

## ***Types***

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

### **Primitive Data Types**

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

## ***Logical Operators***
|Operator|Description|
|---|---|
|`&&`|and|
|`[double pipe]`|or|
|`!`|not|

**Should not** use logical operators for non-primitive types,

`"cat".equals("cat")` rather than `"cat" == "cat"`

## ***Control Flow***

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

## ***Arrays***

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

## ***ArrayList***

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
|Find if list contains (boolean)|`~ .contains(value)`|

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

## ***Loops***

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

## ***Useful Methods***

**String**

|Method|Syntax|Extra|
|---|---|---|
|Find value of character| `String.charAt([index])`| finds the character at index of string e.g. beginning character|
|Upper and lowercase| `~ .toUpperCase() / .toLowerCase()`|

## ***Object Oriented Programming***

*Name of class must begin with capital letter and match file name !!*

|Parts|Description|
|-----|--------|
|Classes| The blueprint of the program that contains the below|
|Class -> State| These are the properties and asstributes |
|Class -> Behaviour| These are the methods (attached to the object e.g .sellArt())|
|Object| Class instances that can use the methods and has the properties defined above|
|Instance variable| Properties that apply to the entire class|
|Local variable| Properties that apply only to the method |

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

**Creating a constructor, properties and behaviours in class Person.java**

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
## ***Testing***

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

**Import classes junit, assert and beforeeach**

```java
import org.junit.jupiter.api.Test;
import org.junit.jupiter.api.BeforeEach;
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

### **Calculator example**

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

## ***TDD (Test Driven Development)***

1. Plan criteria for the code to pass
2. Write tests for the code
3. Write code that passes the tests

E.g. FizzBuzz problem :

- any number divisible by 3 should give back fizz
- any number divisible by 5 should give back buzz
- any number divisible by both should give back fizzbuzz
- any number not divisible by either should give back the number itself

*FizzBuzzTest.java*

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

*FizzBuzz.java*

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

## ***Multiple Classes***

### **Chicken Farm Example**

Chicken Farm UML (Planning Phase)

![Chicken Farm UML](/images/chicken_farm.png "Chicken Farm UML")

Refer to Github code! It's too much to paste here. The class diagram should be updated with arguments and outputs.

### **Art Gallery Example**

***Acknowledgement:*** Thank you Lamees for putting up with my hecticness as we tackled this paired programming lab. I am happy that we worked together to get the MVP done before dinner time through our seamless teamwork. I hope we get to work together again during the rest of the bootcamp.

![Art Gallery UML](/images/art_gallery_classdiagram.png "Art Gallery UML")

### **General Layouts**

*For TDD (test driven development)*:

*ClassTest.java*

```java
[                         ] // IMPORTS

public class GalleryTest{

    [          ] //Properties that need to be accessed e.g. Gallery gallery

    @BeforeEach
    [              ] //Setup scenario that you want to test on
    [              ] // e.g. gallery with artworks added
    [              ] // gallery = new Gallery(String name);

    @Test
    [              ] //Create tests that you want your methods to pass

    @Test
    [              ] //e.g. assertThat(gallery.getTill).isEqualTo(20)
}
```

*Class.java*

```java
[                         ] //IMPORTS

public class Gallery{

    [              ] //PROPERTIES
    [              ]

    public Gallery(String name){ //CONSTRUCTOR
        [               ] //assign the initial values .e.g this.name = name;
    }

    [              ] //BEHAVIOURS (or methods)
    [              ] // e.g. public void setName(){    }
    [              ]
    [              ]
}
```

## ***Inheritance***

### **Zoo Example**

![polymorphism](/images/polymorphism.png)

*ParentClass.java*

```java
public abstract class Animal {  //abstract class means no longer able
                                //to make new Animal class, instead make lion
                                //or parrots
    //PROPERTIES

    protected String name; //like private plus, available to class and extended 

    //CONSTRUCTOR

    public Animal(String name){
        this.name = name;
    }

    //BEHAVIOUR

    public String makeNoise(){
        return "Hello, my name is " + this.name + ".";
    }

    public String eat(){
        return "Mmmm, that was tasty!";
    }

}
```

*ChildClass.java*

```java
public class Lion extends Animal{  //extends to parent class

    //PROPERTIES (specific to lion class)

    private boolean canWaitToBeKing;
    private double jumpHeight;

    //CONSTRUCTOR

    public Lion(String name, boolean canWaitToBeKing){
        super(name); //HAS TO BE FIRST
                     // whatever the parent class does, this does it too
        this.canWaitToBeKing = canWaitToBeKing;
    }

    //BEHAVIOUR

    @Override // optional tag, but clearer to external reader
    public String makeNoise(){ //overrides parent method
        return "ROAR";
    }
}
```

Therefore methods in parent class can be called by lion,

e.g. `lion.makeNoise(), lion.eat()`

At the same time, new methods can be added specifically to lion that makes it unique to other animals that may override the parent method just for that class.

More child classes can be added, refer to GitHub code for parrots.

Making parent class abstract means you can no longer directly test it, therefore AnimalTest.java is no longer needed.

### **Inheritance Chan**

We can make multiple super classes for further categorisation. Longer inheritance chains can be a con so be careful with the length of your inheritance chain.

![polymorphism](/images/inheritance_chain.png)

If subclass has two inheritance chains, we encounter the "Diamond Problem". A class **can not** extend to multple parent classes in Java. However other languages such as C++ and Python will allow you to extend to multiple.

The # is for protected which means property is accessible from class and also extended classes.

### **Inheritance Extras**

|Concept|Implementation|Description|Real Example|
|----|-----|-----|-----|
|Abstract Class|`public abstract class Cake`|Creates an abstract class that can't be called but provides the common properties for subclasses (child classes)|
|Method Overload|`setMessages(String) , setMessages(String, int, String)`|Methods with the same name but different set of arguments are allowed, also can take in different datatypes|Login type for websites e.g. login with google, facebook, username and password... etc|
|Abstract Method|`public abstract double getSellPrice();`|Super class has an abstract method that has to be implemented and defined in all subclasses|
|Interface|`interface Extras{public int getEggsNeeded();}`|Creates an interface that subclasses can 'implements' to rather than extend to. This creates a loose coupling.|

*AbstractClass.java*

```java
//Cake.java
public abstract class Cake{}

//Cheesecake.java
public class Cheesecake extends Cake{}
```

*MethodOverload.java*

```java
    public void setMessages(String message1){  //OVERLOADED METHODS
        this.decorativeMessages = new ArrayList<>();
        this.decorativeMessages.add(message1);
    }

    public void setMessages(String message1, String message2){
        this.decorativeMessages = new ArrayList<>();
        this.decorativeMessages.add(message1);
        this.decorativeMessages.add(message2);
    }
```

*AbstractMethod.java*

```java
//Cake.java
    public abstract double calcSellPrice();

//RedVelvet.java
    public double calcSellPrice(){
        return 5.50 + this.layers; //price is now dependent on layer count
    }
```

### **Setting Up Interfaces**

Packages are used to organise the java files. In the Championship example we have models and interfaces to sort out the files, however we can name the packages for model differently. Interfaces are usually name `"I + [related class]"`.

Firstly, we create an interfaces package and create ICycle in that package.

***Access modifiers are redundant for interface methods***

```java
//ICycle.java
package interfaces;

public interface ICycle {

    String cycle(int distance);
}

//Cyclist.java
package models;
import interfaces.ICycle

public class Cyclist implements ICycle{
    
    private String name;

    public Cyclist(String name){
        this.name = name;
    }

    public String cycle(int distance){
        return this.name + " cycled " + distance + "m";
    }
}
```

### **Using Interfaces as Variable Type**

```java
public class Championship {

    private String name;
    private ArrayList<ICycle> cyclists;
    private ArrayList<IRun> runners;
    private ArrayList<ISwim> swimmers;

    public Championship(String name){
        this.name = name;
        this.swimmers = new ArrayList<>();
        this.cyclists = new ArrayList<>();
        this.runners = new ArrayList<>();
    }

    public void addSwimmer(ISwim swimmer){
        this.swimmers.add(swimmer);
    }

    public ArrayList<ISwim> getSwimmers(){
        return this.swimmers;
    }

}
```

This makes it possible to add swimmers and triathletes into the same arraylist as they both use the interface ISwim.

### **When To Use Interfaces and Super Classes**

For common properties, super classes, abstract class and inheritance are more suitable.

For common behaviours, interfaces are more suitable.

### **Bakery Example**

Code is on GitHub under bakery_lab.

![bakery](/images/bakery_lab.png)

|Annotation|Meaning|Description|
|---|---|----|
|Blank arrow & solid line|Extends|Subclass extends to superclass|
|Solid line|Connected|Related classes however best to add a note on top of line e.g. Bakery --- has many --- Cake|
|Dotted line & blank arrow|Implements|Class implements the interface|
|-, +, #|Private, Public, Protected|Class properties and methods accessibility outside|

By default, everything should be private and then changed to protected if needed. Private is there to make sure you or collaborators do not mess it up. If by default, protected, more chances to mess up in subclasses that extend to the superclass.

Object Type Number of Methods Available:

- RedVelvet
- Cake
- ISell

## ***Association***

There are two types of association: **comopsition** and **aggregation**

![association](/images/association.png)

Purely inheritance:

![tightly coupled](/images/tightly-coupled-hierarchy.png)

Interfaces are introduced for a more scalable code with association lines:

![loosely coupled](/images/composition-loose-coupled.png)

|Annotation|Meaning|
|---|---|
|Solid line & filled diamond|Composed Of|
|Solid line & blank arrow|Aggregation|

**Example Code**

baseProduct is an IProduct data type that uses the IPart interface, hence Part needs to implement IPart. However, everything else that is non unique to baseProduct is in IProduct. The implementation of IPart and IProduct on the baseProduct is exampled below.

*Implements of Part to IPart:*

```java
public class Part implements IPart {

    private String manufacturer;
    private long partNumber;
    private IProduct baseProduct;

    @Override
    public String getManufacturer() {
        return manufacturer;
    }

    @Override
    public long getPartNumber() {
        return partNumber;
    }I
}
```

*Composition of IProduct to Part:*

**CTRL + O** - to override methods from IProduct

```java
    @Override
    public float getPrice() {
        return this.baseProduct.getPrice();
    }

    @Override
    public long getInventory() {
        return this.baseProduct.getInventory();
    }
```

## ***Algorithms and Big O Notation***

***AKA Data Structure and Algorithms (DSA)*

These are step by step procedues for solving a problem which are reusable. In JavaScript these are functions, in Java these are methods.

### **Big O Notation**

Used to compare algorithms based on:

- **TIME** - how many operations are performed
- **SPACE** - memory allocation (not the cost it used to be)

The Big O notation questsions how scalable the algorithm is based on the magnitude of the input. Simple operations include multiplication, addition, division, assignments, comparisons... etc.

This is used to focus on general trend of the algorithm.

 ***Example 1a (Linear Time)*** 

 *Add all numbers up to n:*

 Option 1.

 ```java
 int sum = 0;

 for (int i = 0; i < n ; i++){
    total += i;
 }
 return total;
 ```

 This code has multiple assignments, increments, comparisons and addition. Inside the loop, these simple operations scale with *n*.
 
 Therefore the general trend of this algorithm is expressed as,

 $$ O(n) $$

where this is a Linear Time, as *n* increases then the time increases at the same rate.

 ***Example 1b (Constant Time)*** 

 Option 2.

 ```java
 int addAllNumbersTo(int n){
    return n*(n+1)/2;
 }
 ```

 This algorithm has 3 simple operations. When *n* is increased the number of simple operations is constant.

 This gives us an algorithm that follows Constant Time, (always same expression)

 $$ O(1)$$

  ***Example 2 (Quadratic Time)***

  *Array of elements to check for duplicates:*

  ```java
  for (int i ; ......){
    for (int j ; .......){

    }
  }
  ``` 

In this algorithm, each for loop scales with input *n*. Since we have a nested loop the general trend is therefore,

$$O(n^2)$$

 ***Example 3 (Logarithmic Time)*** 

This is where the problem scales by,

$$O(log_x n)$$

as the magnitude of the input increases, the rate of the scale of time decreases. A great example of this kind of algorithm is the **Binary Search**. When finding your name in a phonebook, you can split the book in half and throw away the half that you don't need and repeat. This requires the phonebook to be sorted alphabetically in the first hand.

### **Overview of Big O Scaling**

![big_o](/images/big_o.png#center)

## ***Stacks and Queues***

Both of these data structures are limited, however for the right situation they can be much more efficient that ArrayLists.

These examples can include a ticketing complaint system of First In First Out or **MTG** spell stack resolving of Last In First Out where both these data structures are better since they focus only on the methods that are needed compared to indexes of ArrayLists.

### **Stacks**

![stacks](/images/stacks.png)

### **Queues**

![queues](/images/queues.png)

## ***Enum***

A collection of pre-defined values e.g. dates, a hierachy ... etc. Can be used to restrict the options that a user might have. Other examples include setting type in DnD weapon damage type e.g. slashing, blunt, piercing.

### **Initialising**

In order to create this, a new enum file is needed,

*Weekday.java*
```java
public enum Weekday {

    MONDAY,
    TUESDAY,
    WEDNESDAY,
    THURSDAY,
    FRIDAY,
    SATURDAY,
    SUNDAY;
}
```

*Booking.java*
```java
public class Booking {

    private String name;
    private int weekNumber;
    private Weekday weekday; //using the weekday enum

    public Booking(String name, int weekNumber, Weekday weekday){
        this.name = name;
        this.weekNumber = weekNumber;
        this.weekday = weekday;
    }
}
```

*Runner.java*
```java
public class Runner {

    public static void main(String[] args) {

        Booking booking = new Booking("Kevin",23,Weekday.MONDAY); //calling from enum

        System.out.println(booking.getWeekday());
    }
}
```

To access the elements of the enum, we can use the following,

```java
        System.out.println(booking.getWeekday()); //gets from initialised booking

        System.out.println(Weekday.values()[3]); //gets the value at index 3 from enums

        for(Weekday weekday : Weekday.values()){ //loops through the values
            System.out.println(weekday);
        }
```

### **Addtional Varieties**

We can add extra parts of the enum that might be translated to a different situation e.g. different language. In the below example, we include the German translations.

```java
//Weekday.java
public enum Weekday {

    MONDAY("Monntag"),
    TUESDAY("Dienstag"),
    WEDNESDAY("Mittwoch"),
    THURSDAY("Donnerstag"),
    FRIDAY("Freitag"),
    SATURDAY("Samstag"),
    SUNDAY("Sonntag");

    private final String german;

    Weekday(String german){
        this.german = german;
    }

    public String getGermanWeekday(){
        return this.german;
    }
}

//Runner.java
for(Weekday weekday : Weekday.values()){
            System.out.println(weekday.getGermanWeekday());
        }
```

## ***Scanners and Exceptions***

Scanners allow inputs like Python `input()`.

```java
import java.util.Scanner;

public class Runner {

    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in); // accepts value

        System.out.println("Please enter your name:");

        String name = scanner.nextLine(); // enter input value here

        System.out.printf("Hello " + name);
    }
}
```

Other variable types can be found in the methods for scanner,

`int number = scanner.nextInt();`

`int number = scanner.nextBoolean();`  ... etc

### **Exceptions**

When something throws an exception, the code needs to be able to handle unexpected or invalid inputs. This is analogous to implementations such as password creation requirements or certain variable type acceptance in a field.

If something might go wrong, put in exceptions. This is analagous to Python `try: , except:`

*ExceptionPractice.java*
```java
public class ExceptionPractice {

    public ExceptionPractice(){

    }

    public boolean checkEven(int number) throws Exception{
        if (number %2 == 0){
            return true;
        }
        throw new Exception("Number is not even.");
    }
}
```

*ExceptionsRunner.java*
```java
public class ExceptionsRunner {

    public static void main(String[] args) {

        ExceptionPractice exceptionPractice = new ExceptionPractice();

        try {
            exceptionPractice.checkEven(5);
        } catch(Exception exception) {
            System.out.printf(exception.getMessage()); //prints message from exception method
            exception.printStackTrace(); //prints the stack trace
        }
    }
}
```

### **Guessing Game Example**

![guessing game](/images/guessing_game.png)

*Game.java*
```java
import java.util.Scanner;

public class Game {

    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);

//        IPlay game = new NumberGuesser();
        IPlay game = new WordGuesser(); //sets the game to the WordGuesser instead!

        System.out.println(game.start());

        while(game.isRunning()){
            System.out.println(game.promptForGuess());

            String guess = scanner.nextLine();

            try {
                System.out.println(game.processGuess(guess));
            } catch(Exception exception){
                System.out.println("That's not a valid guess, try again.");
            }
        }

        System.out.println("Well done, thanks for playing!");
    }

}
```

For WordGuesser.java, look at GitHub code.

*IPlay.java*
```java
public interface IPlay {

    boolean isRunning(); // checks if the game is running
    String start(); // don't want scanner tied to the game logic
    String promptForGuess();
    String processGuess(String guess) throws Exception;
}
```

*NumberGuesser.java*
```java
import java.util.Random;

public class NumberGuesser implements IPlay{

    private boolean running;
    private int secretNumber;

    public NumberGuesser(){
        this.running = false;
    }

    public boolean isRunning() {
        return this.running;
    }

    public String start() {
        Random rand = new Random();
        this.secretNumber = rand.nextInt(1,101); //random number between 1-100
        this.running = true;
        return "Welcome to the number guessing game!";
    }

    public String promptForGuess() {
        return "Enter a number between 1 and 100: ";
    }

    public String processGuess(String guess) throws NumberFormatException {

        int parsedGuess = Integer.parseInt(guess);

        if (this.secretNumber == parsedGuess){
            this.running = false;
            return "Congratulations, you've guessed correctly!";
        }
        if(this.secretNumber > parsedGuess) {
            return "Sorry, your guess was too low.";
        }
        return "Sorry, your guess was too high.";
    }
}
```

[Back to Top](#java-cheatsheet)

## ***Appendix***

### ***UML Cheatsheet***

![UML Cheatsheet](/images/UML_cheatsheet.jpg)

[Back to Top](#java-cheatsheet)