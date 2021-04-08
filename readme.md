## Functional Programming in java
Rule number one : Before Learning any new thing you should learn what is it? and why we need to learn?
So, our first question is what is it?
Here is the Answer Maybe google will give me much more theoritical defination but i'm no google 
So, Functional programming means writing clean code. how the question is now? by using lambda expression and functional interface, we will cover this topic in detail.
Funtional Programming is a way of thinking and creating pure functions

Why we should learn Functional Programming?
Well, I'll give you one good reason if you want to convert your function into single line of code you should use functional programming, right now this is enough for you later you will understand everything.

## Table Of Contents
* [Introduction](https://github.com/hrk00007/Functional-Programming-Java#introduction-to-functional-programming)
* [Lambda Expression](https://github.com/hrk00007/Functional-Programming-Java#lambda-expression)
* [Functional Interface](https://github.com/hrk00007/Functional-Programming-Java#functional-interface)
* [Lambda Expressions with Multithreading](https://github.com/hrk00007/Functional-Programming-Java#multithreading-using-lambda-expressions)
* [Lambda Expressions with Collections](https://github.com/hrk00007/Functional-Programming-Java#lambda-expression-with-collections)
* [Anonymous Inner Class vs Lambda Expressions](https://github.com/hrk00007/Functional-Programming-Java#anonymous-inner-class-vs-lambda-expressions)
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

oK now let's how will happen if we give two abstract method in fucntional Interface Let me show you ScreenShot 2
> ![image](https://user-images.githubusercontent.com/67812755/113496248-5e11aa80-9515-11eb-9cd2-b192f2acb459.png)

by giving those @functionalInterface annonation compiler check whether the given interface conatain one single abstarct method or not in this case it's not so compiler give us an error. I hope by this point you have much more clarity what is functional interface. 
### Let cover some few important cases of Functional Interface 
> Case 1:
> 
![image](https://user-images.githubusercontent.com/67812755/113496832-44736180-951b-11eb-9a3c-d2f8965a5996.png)

> Explanation: If parent interface contain one single abtsract method then we should not declare the same abstract method twice we can use from parent class
>

> Case 2:
> 
![image](https://user-images.githubusercontent.com/67812755/113496912-04f94500-951c-11eb-8617-7c760883850f.png)

> Explanation: If parent interface contain one single abtsract method and even if we declare the same method in child interface we will not get any error 


> Case 3:
> 
> Question: What if we given parent interface different single abstract method and child interface single different abstract method
> 
![image](https://user-images.githubusercontent.com/67812755/113496971-a1bbe280-951c-11eb-9f1e-199335cbbc8f.png)

> Explanation: If parent interface contain one single abtsract method and  if we declare the different abstract method in child interface we will not get an compile time error
> saying 
>
> Compile Time Error(CE):  B is not an functional interface multiple non-overriding abstract method found in interface B  

### As we look some of the edge cases of functional interface and let's do some real programming

_**Code number 1(Functional Interface without lambda)**_
> 
> ![image](https://user-images.githubusercontent.com/67812755/113502766-f75bb380-954b-11eb-8cd8-b12ba837859d.png)

Okay so that approach is traditional, you aren't here for that I know. Let's convert piece of code into concise code
> HERE WE GO! BABY _**Code number 1(Functional Interface with lambda)**_
> ![image](https://user-images.githubusercontent.com/67812755/113502901-77821900-954c-11eb-8ce8-7a2597111748.png)
>
> Now, this is what i call functional programming but this is just a start we are going to do much more awesome things together 
> 
> Enough of your little happiness let's move to _**CODE NUMBER 2**(functional interface with two argument and without Lambda Expression)_
> 
>![image](https://user-images.githubusercontent.com/67812755/113503280-7b169f80-954e-11eb-8fe4-12d04ad2c0ca.png)
>
Okay, now you know that we will do we will convert this into Lambda Expression
>
>_**CODE NUMBER 2**(functional interface with two argument Lambda Expression)_
>![image](https://user-images.githubusercontent.com/67812755/113503164-b82e6200-954d-11eb-9bf2-0402589aa77b.png)
>
This is how you do it when you want to work with parameter with lambda Expression. Are you tried? because we are not over it? Still one more thing to cover. Yeah! You got it
how to deal with return type in Lambda Expression. Don't Worry brother I got you.

> **_Let's move toward to last thing you should know about Lambda Expression with return type_**
> _**Code number 3(Functional Interface with return type and without lambda)**_
>
>
>![image](https://user-images.githubusercontent.com/67812755/113503574-58858600-9550-11eb-8b93-78a989662aef.png)
>
> Okay, now you know that we will do we will convert this into Lambda Expression
> 
>![image](https://user-images.githubusercontent.com/67812755/113503781-a3ec6400-9551-11eb-8244-3400e90b0604.png)
>
> Okay so everyting you should about the basics of Lambda Expression and Funtional Interface we covered it (Let's take this course to some advance level)
> You can take some Exercises:
> 1. Write two lambda Expression for square and cube
> 2. Make a simple calculator using lambda expression
> 3. Write a lambda Expression  and pass a argument and tell whether the given number is EVEN or ODD
>

## Multithreading using Lambda Expressions

> **Code number 1(Implementing Runnable interface using normal approach)**
> 
>
>We all know this aproach but if you want to notice something you can remember that Runnable is a functional interface, really YES! it contain only one single abstract method
>run() which make him a functional interface, have a nice look on this code in the next image you will seeing lambda expression with Runnable interface
>
>
>![image](https://user-images.githubusercontent.com/67812755/113511185-3275db00-957c-11eb-9e74-c84a5438cd1f.png)
>
>
>**Let's Convert (lambda expression with Runnable interface)**
>
>So, as you know or I'll say if you know multithreading the output will vary OS to OS and every time you run because both main and child thread priority are same
>
>![image](https://user-images.githubusercontent.com/67812755/113511281-b8922180-957c-11eb-896f-f556141fd156.png)
>
 If you able to adapt this simple multithreading concept then Congragulation! it will really help you to become a good java programmer like me! Just Kidding 😂
 Enough of this shitty joke let's move toward the important concept of Lambda Expression with Collections ! OOOOHHHHHH YEAH  ❤

## Lambda Expression with Collections
Before starting to Lambda Expression with collection. Let me cover some Comparator concept if you know it you can skip but don't skip it will be amazing.
> Comparator:
> 
> Comparator is an functional interface which means it has only one method and we all know that is _**int compare(Object obj1,Object obj2)**_
>
> 1. return -1 if obj1 has to come before obj2
> 2. return 1 if obj1 has to come after obj2
> 3. return 0 if obj1 and obj2 is equal
> 

> ![image](https://user-images.githubusercontent.com/67812755/113518221-8dbac400-95a2-11eb-8c64-8b343c780ce2.png)

**In order to sort in ascending order we can go though this but what will we do if want to sort in Descending Order**

> Here is what we can do 
> 
> ![image](https://user-images.githubusercontent.com/67812755/113517864-2ef44b00-95a0-11eb-8125-523d5a438255.png)

> Since you are here with me all the time let me give you a gift you deserve that right!
>
>
> Here it is
> 
>![image](https://user-images.githubusercontent.com/67812755/113518118-e8075500-95a1-11eb-9cdb-95bae485c454.png)
>
> I don't need to tell you what are those if your fundamentals of programming are clear!
> 
>Now we will convert this comparator functional interface using lambda Expressions
>
>
![image](https://user-images.githubusercontent.com/67812755/113552829-584ebe80-9614-11eb-9d9b-ae0548d60e5e.png)
>

> If you know Streams the next example can really help you ,Otherwise it will be uploaded soon in my github repo under the name Streams in java
> 
 ![image](https://user-images.githubusercontent.com/67812755/113553166-ef1b7b00-9614-11eb-9583-ab64ef817ed4.png)
> 
> If you don't get this don't worry we will learn streams in java in the next article 
> 
> This is all about number kind of thing. Let me take some real life example problems so you will get hands on some major advantages of lambda Expressions
> Here is Eg 1: 
> In this example we are sorting in ascending order of empno 
>
![image](https://user-images.githubusercontent.com/67812755/113554043-5128b000-9616-11eb-81fe-d63c9951632e.png)
>
>
> Here is Eg 2: 
>In this example we are sorting in ascending order of empname (we are using comparable which is also a functional interface contain compareTo method)
>
![image](https://user-images.githubusercontent.com/67812755/113554321-c4cabd00-9616-11eb-9f23-14ab524b8997.png)
>
>
> 

So this is all about **Lambda Expression with collections!**  Hope your learning amazing things from here

## Anonymous Inner Class vs Lambda Expressions

Some of you may know what are inner class or don't. I am considering as you don't know what are inner classes so let me give you an eg;
>
>
>![image](https://user-images.githubusercontent.com/67812755/113568917-1bdc8c00-962f-11eb-8c54-15e87f7681cf.png)
>
> You can see that runnable it doesn't end with semicolon it contain the whole body of a class, now that is what java people called Inner class.
> 
>Now let's move towards Lambda Expression one
>
> ![image](https://user-images.githubusercontent.com/67812755/113569122-8f7e9900-962f-11eb-84ee-b40b6e0c0715.png)
> 
> Now this is what they called Lambda Expression 
> 
> Don't you dare to think that they are same. They are definetly not. Okay!
> 
> If you still not beleive let me tell you an example
>
> ![image](https://user-images.githubusercontent.com/67812755/113569686-8d690a00-9630-11eb-848d-310c6029f79f.png)
>
>
> If your interface contain two abstract method we can't go for lambda Exression but we can use Inner classes in such cases
> So,Here are some of the points of these section you should always remember
> * Anonymous Inner class can extend a normal class
> * Anonymous Inner class can extend a abstract class
> * Anonymous Inner class can implement an interface which contains any number of abstract method
> * Lambda Expressions can implement an interface which contains a single abstract method(FI)
> * Anonymous Inner class != Lambda Expression
> * Anonymous Inner class> > Lambda Expression

##### Before we start the next section. I'll tell you something important that we are taking a deep dive in some real functional programming. So be carefully with it.

### Predefined Functional Interface: _**Predicate**_

**What is a predicate?** 
_**Ans:**_ Predicate is a functional interface, which accepts an argument and returns a boolean. Usually, it used to apply in a filter for a collection of objects.

In this code we are going to peform a condition checking operation whether the given number is even or odd. We are writing a boolean function which returns true if the number is even and false if the numbers is odd

![image](https://user-images.githubusercontent.com/67812755/113651613-efb51f80-96af-11eb-84e8-6d8b4d0010c7.png)

> Okay now we will convert this code into predicate by implementing predicate Interface
 
> In the next code we are implementing the predicate interface which is a functional interface with only one single abstract method named **test** which will check the condition and return true or false
> 
 
>![image](https://user-images.githubusercontent.com/67812755/113651929-8386eb80-96b0-11eb-840e-d01b88c95be8.png)

Okay now we will convert this code with Lambda Expression

> See how easy it is and look at the code simple and clean.Now that is called Functional Programming
> 
![image](https://user-images.githubusercontent.com/67812755/113652266-17f14e00-96b1-11eb-91a2-88aab6d674cc.png)

We take those numerical type example. Let me cover some real life example so you will get some real clarity on predicate

> Look at this code carefully. I created a employee class which contain three data member empid,ename,salary and all those constructor and getter,setter. You know that stuff don't you. Yeah Right!
> Now you will check whose salary is greater than 1000 and we will print there name and that boolean output
> 
![image](https://user-images.githubusercontent.com/67812755/113746688-39d7e880-9724-11eb-9e24-031930b6fae7.png)

Hope you get this example let me cover one last example in predicate which is really underrated concept
In java 1.8 in interface we can declare default() and static() method also any number of time we want. So in predicate there are some default method you should aware of and 
it might help you sometimes

> Look At this Image Carefully from JAVA SE 8 DOCS
> ![image](https://user-images.githubusercontent.com/67812755/113748138-c46d1780-9725-11eb-8f22-95daa5410122.png)
> test is an abstract method but other than test there are some methods we are going to cover it all in one single example.
> Look at this code now
Here p1 predicate check whether the given number is odd or not
Here p2 predicate check whether the given number is greater than 10 or not
>
>
 ![image](https://user-images.githubusercontent.com/67812755/113749157-f2069080-9726-11eb-92cb-ff7ce35582a3.png)
> 
> In the line 1 or first for loop we are checking both the condition of p1 and p2 should be two i.e number should be odd and greater than 10 also (45,85).
> 
> In the line 2 or second for loop we are checking either of the condition of p1 and p2 should be two i.e number should be odd or greater than 10 also (12 45 26 85 5 7 ).
> 
> In the line 3 or third for loop we will get the opposite of the output in that case our output should be (45,85) but we are exactly opposite ( 12 26 5 7 8 ).
> 
>
So this is all about Predicate functional interface! Hope you are having a Good time 😍❤

### Predefined Functional Interface: _**Function**_
If you are here from starting it means you know how we converted our normal codes into Lambda Expression. But we will grasp the speed now. Okay! Well if you not agree than also you don't have a choice here 😂😂 

> Now in the last section of predicate we check that we can perform some test operation true or false type, but what if we want to perform some operation like square,cube etc.
> Well in such cases we can go for functional function interface Yass you heard it right!.

Let me take an example
>
In the first f1 function we are taking an integer as input and returning it's square 
>
In the second f2 function we are taking an string as input and returning it's length
>

> ![image](https://user-images.githubusercontent.com/67812755/113758813-fa17fd80-9731-11eb-829a-007d12c1520e.png)
>

> 

> **Example Number 2 (V.V.V.V Imp )**

> 
![image](https://user-images.githubusercontent.com/67812755/113759839-2da75780-9733-11eb-853a-a10e8e0d0837.png)

In this code we have a function f1 which take student as argument string as return type and we are returing grade from f1 interface
And then we take a predicate which we learned in last lesson and we are checking those student who got marks more than 75%. 

And now we are done with functional function interface! No WAIT! In the last topic predicate we cover some default method in predicate there are some default method in function interface also.

>
Those are some method let me take an example so that those function will also covered 
>
![image](https://user-images.githubusercontent.com/67812755/113796927-e68a8800-976d-11eb-9f19-69ef7a0a0569.png)
>
Those comments will help you to understand that example quickly

>

>![image](https://user-images.githubusercontent.com/67812755/113797222-7d574480-976e-11eb-82c5-18f372d1ed0f.png)
>

>

### Predefined Functional Interface: _** Consumer **_
Consumer: Consumer<T> is an in-built functional interface.It take an argument of any type and perform operation without reuturing any thing.
 >
  
 > 
  Look at this example from last section we will add some more functionality here by using Consumer
  
  >
![image](https://user-images.githubusercontent.com/67812755/113798132-3702e500-9770-11eb-8af4-5e297c49d591.png)
>
This is a really big example. Let me tell you line by line 
From line 52 -- 68 there is a function which take Student as an argument and string as return type and we are calculating there grade. we take the same example in the last section if you want to check again! Surely you can revisit.
>
>
69-74 We created a student array with 4 students as you can see
>
>
In the line ---76 predicate we are filtering the student and checking who are those student got marks greater than 75% and it will return true or false. we take the same example in the Predicate section.
>
>
Now comes the most important part Consumer. It is doing nothing just printing the value and calling the function. In the shorthand people say it consumes everything
>
And last but not the least we are calling predicate test in if condition inside for loop and if the condition is true we are  printing those student data.
>
> This is how we work with Consumer.
> Now let me cover some default method in Consumer functional interface

  ![image](https://user-images.githubusercontent.com/67812755/113801487-8ea44f00-9776-11eb-8152-f3d98d24d488.png)
  >
Read those comments of the code and you are good to go!.
>
>

This is all about Consumer And let's move forward to last importnat topic **Supplier**

>
>
**Supplier : ** It represents a function which does not take in any argument but produces a value of type T.
>

>In the non-techincal defination it doesn't take any argument and can be return anything according to the programmer's requirement.
Let's see by an example:
>

>
 ![image](https://user-images.githubusercontent.com/67812755/113802557-8a793100-9778-11eb-9904-4427c4ddb95e.png)
>
>

 That's all about predifned functional Interface but if you understoond those next topics will be way to easy for you. Let's check out How but before go through this
 
 > Predicate --> test() 
 > 
 > Function ---> apply()
 > 
 > Consumer ---> accept()
 > 
 > Supplier ---> get()

### BiPredicate
>
>
 The only difference between predicate and biPredicate is predicate can take single argument and BiPredicate can take two argument. Let's see an example
>
>
![image](https://user-images.githubusercontent.com/67812755/113906611-0cf20700-97f2-11eb-8834-223a081a1552.png)
>
Some real life example you can use.YEAH! let me take that
>

>
>
### BiFunction
>
>
Okay so now I am going to copy paste previous defination! Don't Jugde 😂😂
>
>
 The only difference between Function and BiFunction is Function can take single argument and BiFunction can take two argument. Let's see an example
>
> It's an hard example look carefully and you will understand it very easily.✔
> 
>
![image](https://user-images.githubusercontent.com/67812755/113907881-84746600-97f3-11eb-8029-c00c0781d097.png)
>
>
### BiConsumer
>
>
 The only difference between Consumer and BiConsumer is Consumer can take single argument and BiConsumer can take two argument. Let's see an example
>
If you wanna know how consumer work look the above section
>
In this example we are taking every employee and raising their salary by 500 rupees and printing all data through for loop we also have a method named populate which add employee to the list. 
>
>
![image](https://user-images.githubusercontent.com/67812755/113912582-eedbd500-97f8-11eb-85c3-41f6be179839.png)
>
>
### BiSuppiler
Sorry! But there is no such thing as BiSuppiler because Suppiler doesn't take an argument so considering this point why should there be a BiSuppiler with two argument.So remember if any one ask about BiSuppiler you can say this.

## Primitive Function Types:
>
>
### IntPredicate
>
>
There may be a question in your mind what we have predicate why we need IntPredicate. Well Predicate can take any type of argument it can be Integer,String,Float,Double but IntPredicate doesn't take an argument it made for only Integer. So if you are sure that what you are passing is an Integer then surely you can go with IntPredicate
>
>
Look at this example and you will understand it.
>
>
![image](https://user-images.githubusercontent.com/67812755/113972043-938cff80-9857-11eb-9f45-c32dbceea767.png)
>
>

