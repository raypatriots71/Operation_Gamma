## Syntax Explained ( 1st proposal ) 
Due to the hierarchical state of the language noted in the purpose, it is designed to return all sub-nodes to its parent nodes. This provides a different perspective to the way methods are constructed and used. 

### Theory

The chaining of methods and declarations in objects make the logic hard to implement, but would add multiple perspectives to the way things are done. Every parent object may have multiple child nodes. A child node may have multiple parents if they are tagged. A classical approach to objects in programming is a variable that has multiple properties that are named and declared, each having their own funcitons/methods. This can be achieved as ( see below Drawbacks ) putting the Object in place soley at the font of each statement. Lets use some code for the visual learners:
```
RandomObjectName.#property1.(6).randomFunction    // multiple inheritance
RandomObjectName.#randomProperty2.(().property1).randomFunction2  // multiple inheritance
RandomObjectName.#randomProperty2.(().property12).(#randomId.randomFunction23)  // our syntactical logic isnt here yet, but will be soon
```
The second example is where the language really shines. 
And here is single inheritance:
```
RandomObejctName.(6).functionFoo     //RandomObjectName has only 1 child
```

The constructors can be moved around, so can the functions, so can the variable, and so can everything. But, everything on the heirchial scale has a type. A ```Type``` is the ultimate defining mechanism.  Everything has a type and they are declared by the content. Ex: ``` 6 ``` is a subset of ```Integers``` which is a subset of ```Array``` which is a subset of ```Type``` ```Variables```. Every declared ```Type``` in the scope of the program has different properties.  

### Basic Syntax

The part that everyone's been waiting for, syntactical sugar explained. 

**Rules**

1. Every type, transport method, etc is chained together with a ```.``` This helps with flow and organization. 
2. Variables are dynamic and are always accociated with objects. 
3. Antyhing enclosed in ```( )``` is automatically returned to parent. 
4. Operators and regex can exist inside ```( )```. 
5. Spaces and Commas are the general delimiters.

**Variable Declaration**

Hyperobject:    ```Initial object construct``` is declared at the beggining of a statement and is chained by commas. Ex:
```
HyperObject1, HyperObject2           //all of these 'variables' are declared
```
They can be used in front of a statement as such: ``` HyperObject1.(1) //hyperobject is now set to 1```

**Function Construction**

A function is an object which is a collection of methods of which can be applied to hyperobjects or certain variables. Functions are preceded by the ```in | In | IN | iN ``` Statement(s). That signifies the chaining and creation of a constructor to an Object. 
```
in functionOne().construct( inside method, variables and expressions can be used) 
```

**Loops**

Loops run only if they meet a conditional, which is defined as ```{ }```. Iterators are present inside of a conditional defined by ```[]```

For loops: ``` {[ ]} ``` Inside a for loop exists a``` _ //also equal 'to'``` ex: ```{[0 to 5]}``` would be ```for i = 0; i < 5; i++; ```

While loops: ``` {[ ] < x}``` . You can iterate inside of the [].



### Translation

Hopefully, or not, the first thing you would notice is that this language has a very particular way of doing things upwards which leads into direct translation to English to ease debugging and learning. It simply allows a new perspective into logic which may be explained in words and vice versa. Some of the proposed direct translations are ( but not yet completed )
```
.					//of
_					//to
,					//and ( very important topic) ( can be ignored by translator ) ( also chaining ) ( and can be a space inside )
{}					//Conditional
=					//Equals ( used in certain cases inside of a ( ) )
;					//Apply
```
So this may be a new concept, but it might as well help in understanding. Some of the concepts are not finished yet. For example:
```
X,
in add(a, b).construct(a + b)
X.(0, 6).add    //returns 6 to X
```
and translated would be 
``` 
X,
in add( a and b ) of construct ( a + b )
X of ( 9 and 6 ) of add     //returns 15 to X
```
Yes, the object literals need new definitions, but it is workable. 

### Drawbacks

With that in mind, and everything being a sub-class of something else ( ie a String being a subclass of an Array ), we run into a certain set of problems such as every function would have no choice but to be added as a constructor to an empty parent object. Here is a demonstration of that in this Syntax: 
``` 
Y,
in functionFoo(a).construct(6+a) //returns 6+a to parent usage of functionFoo
Y.(6).functionFoo // would return 6 to Y
```
It fails in the aspect of ```.construct(6+a)``` being applied to a different function because it is declared anonymously. One potential solution to this would be to introduce tagging to constructs of functions such as ```@ construct(6+a).(#.randomID)```. In this case, the constructor would be declared globally yet the ID is placed under the function as it is a property of it. 

### Example Code

Finally we get to the part where you can simply just translate existing code to prove your point. I will use C++ as a reference.

C++:
```
#include <iostream>
using namespace std;

int main()
{
  int a, b, total ;
   
   cout << "Input numbers to be added: " << endl;
   cin >> a >> b ;
   total = a + b ;
   cout << "The sum is " << total << endl;
   return 0;
} 
```
S1:
```
Scope.#packageC.extend                    //adds the c wrapper library
a, b, total				//how does compiler know its a var and not wrong syntax?
(Numbers to be added).printf
a.stdin b.stdin        			//maybe put this in 2 diff lines?
total.(a+b)					// so dot means '=' and apply to fn and append and everything? k
(The sum is ).total.printf
```
C++:
```
#include <iostream>
using namespace std;

// AreaTriangle function prototype
float AreaTriangle(float base, float height); 

int main()
{
   float side, segmentHeight, hexagonArea;
   float cosTheta = 0.866025;

   cout << "Program to calculate the area of a hexagon" << endl;
   cout << "Enter side of hexagon: ";
   cin >> side;

   // Base of triangle is equal to side, height is side*cos(30)
   segmentHeight = side*cosTheta;

   // Function returns area of segment. 6 segments for total area.
   hexagonArea =  6.0 * AreaTriangle(side,segmentHeight);

   cout << "Area of hexagon = " << hexagonArea << endl;
   return 0;
}

// AreaTriangle function definition
float AreaTriangle(float base, float height)
{
   float area;
        
   area = (base*height)/2.0;
   return area;
}
```
S1:
```
Scope.#packageC.extend						//is packageC a thing or do we make it?
side, segmentHeight, hexagonArea, costTheta.(0.866025)			//again, fix var declaration
(Program to calculate the area of a hexagon).printf
(Enter side of hexagon).printf
side.stdin
segmentHeight.(side*cosTheta)
hexagonArea.(6(side segment).AreaTriangle)
(Area of a hexagon).hexagonArea.printf
in AreaTriangle( base, height).contstruct(                          //its probably construct not contstruct
	(base*height)/2
)
```

requests:
sample code for loops

### Loop Examples

```
({[0 to 5]}			.   											dot
then?
```
how do we write the body of the loops? otherwise, looks good. we can work on switch and stuff if you'd like

```
use type; //import library 'type'
use io; //import ''input and output'
use math; //import math fns

type_Int name = value;
type_String name = "value";
type_Char name = 'value';
type_Bool name = 'value (0 or 1 OR true or false)';

Array type_Char name(size) = [e, l, e, m, e, n, t, s];
Array type_Char name(size) = [e, l, e, m, e, n, t, s];

*declare int x, y*


x = y;              // assignment =

if x == y .. etc          // conditional ==



if [condition]:
    code;
else:
    code;



for x to y x++:
    code;




while [condition]:
    code;  


do:
    code;
while[condition];

switch[conditional](case1 code)(case2 code)(case3 code)

-----math------
add();
sub();
mult();
div();
pow();
sqrt();
```
