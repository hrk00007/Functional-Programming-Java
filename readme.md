## Functional Programming in java
Rule number one : Before Learning any new thing you should learn what is it? and why we need to learn?
So, our first question is what is it?
Here is the Answer Maybe google will give me much more theoritical defination but i'm no google 
So, Functional programming means writing clean code. how the question is now? by using lambda expression and functional interface, we will cover this topic in detail.
Funtional Programming is a way of thinking and creating pure functions

Why we should learn Functional Programming?
Well, I'll give you one good reason if you want to convert your function into single line of code you should use functional programming, right now this is enough for you later you will understand everything.

## Table Of Contents
* Introduction
* Lambda Expression
* Functional Interface
* Lambda Expressions with Multithreading
* Lambda Expressions with Collections
* Anonymous Inner Class vs Lambda Expressions
* Default method() 
* Static method()
* Predefined Functional Interface
  * One argument predifined  
    * Predicate
    * Function
    * Consumer 
    * Suppiler
  * Two argument predifined  
    * BiPredicate
    * BiFunction
    * BiConsumer
  * Additional predifined  
    * IntPredicate
    * IntFunction
    * IntConsumer 
    * DoublePredicate
    * DoubleFunction
    * DoubleConsumer etc...

### Introduction To Functional Programming
Well, this article is not just about functional programming we are going to cover lots of new features of java 1.8. Some of the questions interviewer can ask about you we'll cover it.So you also get much more clarity.
Java 8 was released in 18th March 2014 where most of the features cover functional programming(it has been before in many languages) java introduced it little late
It means write concise code(giving a lot of information clearly and in a few words) directly proportional to convert piece of block into single line by using Lambda Expression and Functional Programming. Let's start with Lambda Expressions

Internet Defination: Functional programming is a highly valued approach to writing code, and it’s popularity is continuously increasing in commercial software applications

### Lambda Expression
Remember rule number one(what & why)
What is Lambda Expression?
It is an anonymous function
    NameLess
    without return type
    without any modifiers
    
 Confused, huh(let's convert normal function to Lambda)

 Eg 1: function with no argument
 
 > public void demo() {
 >
 > > System.out.println("Code without Lambda Expression");
 >
 > }
  
 
 Converting this into Lambda Expression

 > () -> { System.out.println("Code without Lambda Expression"); }



Eg 2: function with argument

> public void demo(int a,int b){
>
> System.out.println(a+b);
>
> }
 

Converting this into Lambda Expression

> (a,b)-> System.out.println(a+b);



Eg 3: function with return type
> public int demo(int a,int b){
>
> return a*b;
>
> }
>

Converting this into Lambda Expression
>(a,b)-> n*n;
>
>(a,b)->{ return n*n;}; // (if you are giving return keyword parenthesis are compuslory)

eg 4: String example
> public int demo(String s){
>
>   return s.length();
>
> }

Converting this into Lambda Expression

> s -> s.length();


Right now this is enough of Lambda Expression but don't worry we still need to cover the codes of Lambda Expression but in order to learn how Lambda Expression works you should learn Functional Interface. Let take a look towards it.

## Functional Interface
Once we write Lambda Expression and execute it goes to Functional Interface which contains only on abtract method. Let me give you little tour of Interface
We all know what are interface in java. An interface only contains abstract method but in functional interface it take only one single abstract method
Examples of Functional Interface you are using but you don't know

**Runnable ===>run()
Comparable ===> compareTo()
ActionListener==> actionPerformed()**

> After 1.8 features an interface can also contain default() and static method we'll cover this topic later in depth.

Take a look of some ScreenShot of FunctionalInterface
> ScreenShot 1

![image](https://user-images.githubusercontent.com/67812755/113495228-b80e7200-950d-11eb-95cf-20b8a2b18349.png)


This is what functional interface look like line 1 is optional but it will tell the compiler to check that given interface is functional interface or not.
