---
layout: post
title:  data structure 01
date:   2019-01-22 08:20
categories: Rowan
tags: data_structure
---

* content
{: toc}


### Gerneric type

```
people = new ArrayList(),

new ArrayList<student>();
```

its important because it's specific no need for debugger.








### iterators
allow you to step through.

a collection (list, set, ...)

its function

<ul>
 <li>efficienty<\li>
 <li>for set: no get method<\li>
 <li>selective remove value<\li>
<\ul>

for loop can work, but not selectively. (for loop is iterator beyond the scene)

```
for(student s: people){
    ...
}
```

```
Iterator <student> it = people.iterator(); \\ iterator is refering to the collection of the people.
while (it.hasNext())
{student s = it.next();
if (s.gpa()<2.0)
it.remove(); \\ use the iterator to remove. do not call it.next twice inside the loop.
}
```

(note:student here is generic type. )



### List

mylist.get(3)
myList.set(4,"joe")

```
myList.add("jim") \\ can be added on, it grows bigger.

myList.add(0, "join") \\ assigned to the 0 position, everything else is shifted.

myList.remove(4) \\ the list shring.
```
*(note: all 3 above can't be applied on array, because array can't be resized)*

### Array

```
myArray[3]
myArray[4] = "joe" // use assignment
```
array and list use different syntax, but the same thing.

Array is not resizable, once size is set, it can't be changed. (need to be predetermined)

### Debugger

1: Step[over]->Run
called method at full
speed.

2: stepInto -> Pause in
called method.

3: continue, or resume. Run at full speed until breakpoint.


### wrapper classes

|primitive type|wrapper class|
|:---:|:---:|
|in|Integer|
|char|Character|
|short|Short|
|long|Long|
|double|Double|

#### the main use of wrapper class in this course.

new ArrayList<Integer>()
grades.add(90); // autoboxing
int g=grades.get(3); auto-unboxing, the get method takes the integer, unbox it and then store it in the new variable 'g'.

### Comparison

```
String student; // student is an object, because String (capitalized)

if(student == "jim")...// don't do it this way.
if(student.equals("jim")) // do it this way, points will be taken off if I use the lousy one.
```
note: read the comment from the above code block.

*In general, how do you remember when to use `==` and `.equal`?*

* use `==` when

1: comparing primitives.
`int x;` // x is a primitive, because it begins with a lower case letter(int)
e.g `if (x==17)`

2: comparing references

`if(student == null)`

* use .equal when comparing objects.

`if (student1.equals(students2))`

*note: every class is subclass of an object*


### diagram

int x;
x = 17;                      x(17)
Student s,s2;               s(null)   s is a reference.     s2
                                |                           |
                                V                           V
s = new Student("jim");       Student                    student    
                            (name "jim")                name("jim")                        
s2 = new Student("jim");                                if(s==s2)  false
                                                        if (s.equals(s2))  true    

### LinkedList Arraylist                                 

anything(methods) you can do with LinkedList can be done on ArrayList.
both are lists.

then why it's necessary to have the two then?

because it has to do with efficiency.


#### ArrayList VS LinkedList

`add(object)`
`add(int, object)`
`remove(int)`

*LinkedList is faster*



`get(int)`
`set(int,object)`

*ArrayList is faster*

*(memorize the above)*

do not use the wrong list or credits will be taken away in this course.

### Program to an *interface whenever* possible.

Interface - class, but no

* method bodies,

* signatures only.

* cannot be instantiated


```
ArrayList<student> roster
    = new ArrayList<student>()
    roster.add(....);
    m1(roster);

void m1(ArrayList<student r>){
    r.get(0);
        :
        :
    m2(r)
}   


void m2 (ArrayList<student> r){
    r.add(...);
       :
       :
    re.remove(17);
}
```
the above is not efficient, a LinkedList is better.

instead, we use interface.

declare student as `List`

```
List<student> roster
    = new List<student>()
    roster.add(....);
    m1(roster);

void m1(List<student r>){
    r.get(0);
        :
        :
    m2(r)
}   


void m2 (List<student> r){
    r.add(...);
       :
       :
    re.remove(17);
}
```
changed to a List it will still work.

now change it to *interface*

```
List <student> roster
    = new LinkedList<student>()
    roster.add(....);
    m1(roster);

void m1(List<student r>){
    r.get(0);
        :
        :
    m2(r)
}   


void m2 (Interface List<student> r){
    r.add(...);
       :
       :
    re.remove(17);
}
```

### Diagram

Interface(List) -> Arraylist
    |
    V
LinkedList
