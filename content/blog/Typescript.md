+++
title = "Typescript"
date = 2019-11-28
+++

### What is Typescript?
----------
- Typescript offers all features of javascript and some addtional features that is Typescript's **type system**.
- Javascript doesn't do the checking that if what type of data we have assign to the variable but typescript does.
- It reduces the chances of bugs by highlighting the unexpected behaviour of the code.
<br>

### Types by Interface
----------
- Javascript doesn't enforces strict rules about the type of data a variable should hold.Typescript provides this extra layer that ensures the variable should have only particular type of data. It reduces the chances of errors.
- e.g.
    #### Typescript

    ```
    let helloworld = "hello world";
    helloworld = 2;     ■ type 'number' is not assignable to type 'string'.
    console.log(helloworld);
    ```

    #### Javascript
    In javascript we can't see the error that number is not assignable to type string.
    ```
    let helloworld = "hello world";
    helloworld = 2;
    console.log(helloworld);
    ```
### Defining Types
----------
- normally we can define the types a particula object should have in javascript but it again does not provide the strict rule for which data type should it have. In Typescript we can explicitly describe the object's shape by using **interface** declaration.


  - Typescript offers all the features of javascript and it adds on top of it it's Type system.
  - Javascript have data like number , string but it does not check the data type when we assigned value to it.
  - Typescript does check this. So it has this Type System thing. But How as we know Typescript knows javascript it uses value as it  types of the variable.
  - Everyting works good now  But we also have design patterns in JS but some desing patterns is difficult for types to be infered automatically.
  - Typescript comes in here it support an javascript extenstion which we can use and develope a some kind of special variable and defined what data types we need for it explicitly. that is INTERFACE and we can now use this :Typename after the variable to conforms that the object should follow this shape structure.

  ***Javascript primitive data type list***
   - boolean
   - number
   - string
   - null
   - symbol
   - bigint
   - undefined

 **Typescript have extra things**
   - any (allow anything)
   - unknown(ensure someone using this type declares what the type is)
   - never(it's not possible that this type could happen)
   - void (function that return undefined or has not return value)

