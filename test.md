# Prefixbox Test

## Short questions

- What is a package? How do you define a package?
	- Like a folder or directory where files are semantically grouped together.
- What is a constructor? When is it executed?
	- A special method that creates an instance of the class when called. It is executed at runtime.
- How do you implement inheritance in Java?
	- I "extend" the class with the parent.
- How do you prevent someone to inherit from a class?
	- I make it "private" or "protected".
- What is a final variable? Where you can assign value to final variables?
	- Its value cannot be changed. Its value is assigned at declaration.
- Specify the available access modifiers in Java and briefly explain them
	- private: can only be accassed from within the class
	- default: can only be accassed from within the same package
	- protected: can only be accassed from the same package or from a subclass
	- public: can be accessed from anywhere
- Briefly explain the mechanism of exception handling
	- In some cases, there is the possibility of runtime exeption that can be foreseen. In these cases, we can deal with these situations by "throwing" and "catching" the "exeption".
- What is the difference between an abstract class and an interface?
	- In an interface, there are no method implementations while in an abstract class, there can be fully implemented methods and only an abstract method is needed.
- What is the difference between Comparator and Comparable?
	- F*ing no idea at the time of writing. 
	- (I looked it up, though. Thanks for asking. As I see it now is that Comparable is defined within the class to be sorted and it can be used on only one dimension/field while Comparator (which is much cooler) is defined in separate classes based on separate sorting dimensions and I can select the one I need in different situations.)
- How Iterable and Iterator interface works? What methods need to exist in a class that implements them? What is their relation to for loops?
	- Also didn't know. But now:
	- An iterable is a class that implements Iterable (interface) like e.g. List. It can be iterated using a for-each loop. Iterable has one method: iterator() that retuns an Iterator. Iterator has hasNext() and next() that can be used to process the next item.

## Programming tasks

You can write your solutions in any language, you can even write pseudo code or
using only your own words.
The point is not to make a perfectly running application, the point is the way
you think!
Don't worry if you miss a semicolon or some parantheses.
You might use the Java stream API for your solutions but none of the exercises
require them

### Palindrom

Write a function which decides whether a text is palindrom(It's the same whether
you read it forwards or backwards). E.g.: abba, rotator, stats.
You might assume that the input string is not null, the length is greater than
1 and less than one million. **Strive for the low memory complexity!**

Example:

```java
public boolean isPalindrom(String input) {
	input to inputCharArray[]
	StringBuilder stringBuilder = new StringBuilder();
	for (int i = 0; i < inputCharArray.length; i++){
		stringBuilder.append(
		inputCharArray[inputCharArray.length - 1 - i]);
	}
	return input.equals(stringBuilder);
}

isPalindrom("alma"); //false
isPalindrom("görög"); //true
```

### Find The Duplicate

You have an array that contains strings. Every item in the array is
unique except one which is present in the array exactly twice.
Write a function which finds the string that is present twice in the array.
You might assume that the input array is not null, the length is greater
or equal to 2 and less than one million. **Strive for the low time complexity!**

Example:

```java
public String findTheDuplicate(String[] input) {
	fori(i=0; i< input.lengthl i++){
		fori(j=i+1; i< input.lengthl i++){
			if(input[i].equals(input[j]){
				return input[i];
			}
		}
	}
	return "No equals";
}

String[] fruitBasket = new String[] { "apple", "banana", "coconut", "durian",
"banana", "elderberry", "fig", "grapefruit" };
findTheDuplicate(fruitBasket); //should return banana
```
---
Eddig tartott az egy oram :-( .
---

### Count The Words

You have a long string that has some meaning on a real language. For example a
whole novel in a single string.
Write a function that counts the occurence of each word inside the string and
writes them to the output in the following format: `word: number of occurences`
You might assume that the input is not null and not empty. The order of the
words on the ouput does not matter.
The solution might be case insensitive, you don't have to differentiate
bwetween capital and non-capital letters.
The punctuation marks and line endings are not part of the words!

Example:

```java
public void countTheWords(String crazyLongString) {

}

String boci = "Boci, boci tarka, se füle, se farka.";
countTheWords(boci);

//Output:
//boci:2
//tarka:1
//se:2
//füle:1
//farka:1
```

### What Is The Output

What is the output of the following Java application? Explain your solution!

```java
package com.mycompany.myproject;

public class Person {
    public String firstName;
    public String lastName;

    public Person(String firstName, String lastName) {
        this.firstName = firstName;
        this.lastName = lastName;
    }  

    @Override
    public String toString() {return this.firstName + " " + this.lastName;}
}

public class Main {
    public static void main(String[] args) {
        int i = 0;
        String s = "apple";
        Person p = new Person("Jonh", "Doe");

        doSomething(i, s, p);

        System.out.println(i);
        System.out.println(s);
        System.out.println(p);
    }

    public static void doSomething(int i, String s, Person p)
    {
        i = 5;
        s += "banana";
        p.lastName = "Rambo";
    }
}

```

## SQL

- What is the PRIMARY KEY?
- What is the difference between CLUSTERED INDEX and NONCLUSTERED INDEX?
- There is a table called `Employees`. Let's assume that the columns exist
and they have the right data type.
What is going to happen if we execute the script and we destroy
the database connection during the execution? What are the possible problems
that might occure?

```sql
BEGIN TRANSACTION

UPDATE Employees
SET Salary = Salary * 1.1
WHERE
    Salary < 250000
    AND IsActiveEmployee = 1
```

## Web and HTTP

- Specify the existing HTTP request methods and describe their usage!
- What are the groups of HTTP response status codes? Write an example for each group!
