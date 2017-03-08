
## Operation_Gamma 
  
**Futile efforts to build a programming language in which everything is returnable**
  
---

 ### Operation_Gamma

> I'll just let others write this up, im lazy ***- Rohan***

### Contributors
*   raypatriots71 - Rohan Ray
*   Kavar814 - Kavin M. Govindarajan
*   mjoy0210 - Joydeep Mukherjee
*   ACSarma - Arun C. Sarma
*   amsraman - Aditya Sundaram
*  amirkhanaursrk - Manav Majumdar
*  ravitejaaechan - Raviteja Aechan
*  themechanicdude - Jason Li
### Purpose
To create a programming language in which everything is returnable.
Heres what I have so far  ( might need some tweaking )
```
. = Of
 _ = to 
 , = Chain (useless)( don't really need it unless it's useful) ( ) 
 {} = Conditional 
 = = Equal  
 ; = ApplyX.(2,3).add //x=5  
```
```
In add(a,b).construct( a + b) //function 
In square(a).construct( a*a) 
In mult( a b).construct(a*b)  
```
### USAGE
```
Y.(X).Square //25
Y.(X).Square,mult // err mult needs 2 terms  
Method.y.(X) //square
Y.method.y.(X) //25
Y.method.y.x //undefined
```
### MORE COde
```
[A] //Meet true iterate 
[0 to 3] // 0 false 1 false 2 false 3 true
{ [A] }( y.y.add) //loop a times within conditional []
Y.6 F.{ [ 0 to 3 ] }(y.(y).sqare) //F= 2,821,109,907,456
```
### FIBBO
```
//Fibbonachi
In fibbonachi(length).construct( 
start.0,c,next, second.1, 
{ [0 to length] }( 
{c lessthan 1 }(next.c);().construct( 
next.(first second).add 
first equal second 
second equal next) )
Fibresult.(6).fibboonachi
```
### THEORY

A preface to the theory, everything in this language is built on returning the object to the parent. So when you put multiple operaters between a , and a ``` ```, the operators dont matter and will be executed from back to the front. This also comes into postfix view of code operators, while math operands will still work the way they are designed to. Not many languages exist soley to move around parents and children and tag functions like this language. But one of the challenges and difficulties that we may face is the problem of memory management and how to allocate spaces for each function and returning objects. Objects still probably need more memory allocation before they are created and the language may supposedly take up more memory at runtime. 

Some theory:``` () ```code resides in this automatically  ( Everything is automatically enclosed in this and this dignifies a pointer of sorts. When something is called between () it points at the location of the thing that is called instead of bringing that here. (Instance.))
```{} Returns object 
; Applies to previous object```
Here is what I have so far:
```
{ condtional } ( true statement ) ;().construct( falsestatement)
```
That is an  If Else statement and it definetly needs some work. Every variable found in it is an object. If its too confusing then just remember this it eliminates typecasting not like javascript that has typecasting
but like 
```Y.(HELLO WORLD) // y's (hello world)``` is of type value and ```Y.(8)``` would still exist as a property of ```Y``` sort of like everything is a tree to declare a variable 
```
Y.(6) //y is set to 6
```
but if you add a contstructor
```
Y.(6).square // the .square returns (36) to the 6 property of Y
```
Everything binds to each other and can be used independantly

Which would make this ```Y.(6).constructor returns .square``` applicable. 

to declare functions you use in  //input
```
{ conditional }

[ from one number to another ( its a loop ) ] 
```
Another thing is that the code can be written psuedo-english but still be back into a codable sort
```
ex. Y.(8).square   // ``` Y of (8) of square constructor 
```
### Other Purposes
The purpose of this programming language is to bind other programming languages together. The other purpose of this language is to add interoperability to OOP and children using returned objects. 
```after writing all of that i realized that constructors are still enclosed in () so it would interfere with order of ops```
And then theres the problem with javascript that i intend to fix   
1. javascript cant compute big numbers
2. javascript confuses async and sync

Here is how functions would be declared
```parent.(anything inside these is returned to the parent)```
so for functions:
```in randomFunctionName( a, b).construct(a + b )```
it returns ```a + b``` to randomFunctionName method
```
Y.(7,6).randomFunctionName //13
```
### Transliteration
And it would transliterate as 
Variable Y of (7 6) of method randomFunctionName

The purpose of transliteration to english is the purpose of coffeescript to javascript. You can code really highlevel stuff while in psuedo-english whereas you can dig deeper into the code with real symbols and code. The point of this is to intstantiate an easier way to read a language and debug it ( even for the compiler) with a psuedo-english frontface. Another example of tranliteration for the language would be 
```
. = Of
 _ = to 
 , = Chain (useless)( don't really need it unless it's useful) ( ) 
 {} = Conditional 
 = = Equal  
 ; = ApplyX.(2,3).add //x=5  
```
this right here. These codes translate to psuedo-english and will definetly help with using and understanding the language. 

![](https://img.clipartfest.com/e69c9ee61e517b2d787996e40068fa5a_gallup-report-finds-coding-to-coding_600-399.jpeg)
```
and lets put it on git so we could have as much supporters as we can
```
