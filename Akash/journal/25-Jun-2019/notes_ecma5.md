## Outline
1. [Types](https://developer.mozilla.org/en-US/docs/Web/JavaScript/A_re-introduction_to_JavaScript#Overview)
   in JavaScript.

2. Conversion from text to number:  
  * [parseInt(x)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseInt)
  * [parseFloat(x)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseFloat)  
  While using above functions parsing happens till the point of invalid character.
  for e.g. launch a browser console and try out the following examples :

    ```javascript
    >>parseInt('123ab')      // 123

    >>parseFloat('12.3ab')   // 12.3

    >>parseFloat('12.ab')    // 12
    ```

  * [Number(x)](https://gomakethings.com/converting-strings-to-numbers-with-vanilla-javascript/#number)  
  If `x` contains non numerical characters then `Number(x)` returns `NaN`.

    ```javascript
    Number('123')    // 123

    Number('123ab')  // NaN
    ```
       
  * Unary operators for conversion from text to number.

    ```javascript
     +'123'    // 123

     +'123ab'  // NaN
    ```

3. `NaN` : Not a Number. Returned from conversion process where non number was encountered.  
    * NaN is Toxic : 
      ```javascript
      NaN + 7 //NaN
      ```
    * Fun fact:
      ```javascript
      typeof(NaN) //guess?

      ```

4. Strings:  
   Sequence of UTF-16 code units. Each code unit is 16 bit. Some single unicode characters comprise of 2 UTF-16 code units in which case length will be 2.

5. `null` vs `undefined`  
  `null` -> delibrate non value assignment  
  `undefined` -> indicates _uninitialized_ variable, the varable does not exist. Type also is undefined.
  Non existant variable is a real scenario in JavaScript DOM manipulation where 
  we try to access the property of some DOM object that does not exist. In that case system throws exception and may break the script execution, because the attribute 
  you will be refering to will be invalid. One possible way forward is something like below:

  ```javascript
  ...
  if(typeof(domObj.level1) != "undefined"){  //if there is no level1 attribute typeof will give "undefined",
                                             //and we only want to proceed when that's not the case
  domObj.level1.attrib = 'xyz'; //level1 attribute exists. we can dig deeper now to access other sub-attribute
  //do something 
  }
  //do something else
  ...

  ```

  ```javascript
  typeof(null)      //"object"
  typeof(undefined) //"undefined"
  ```

6. Booleans 
  Any value in javascript has a boolean conversion possible.
  
  false, 0, empty string (""), NaN, null, undefined --> false (falsy values)
  
  anything other than above is convertible to true. (truthly values)

7. Declaring variables - `let`, `const` and `var`  (ES5) (to check : arrays objects w.r.t. `const`)

8. Concept of scope in JavaScript.

9. Coersion + Evaluation 

   e.g. 
   ```javascript
    '3'+ 4 + 5 --> "345"
     3 + 4 +'5' --> "75"
   ```
   We can relate the _double standard_ of `+` as seen above to the concept of **operator overloading**.

10. Comparisons:

  `==` vs `===`

  ```javascript
  
  123 == '123' //true 
  1 == true    //true
  ```

  ```javascript
  123 ==='123' //false
  1 === true   //false
  ```
  Similarly there are javascript inequality operators:
  `!=` , `!==`



11. Control structures  
 Similar to C family  - _if_, _if-else_, _if-else-if_, _while_, _do..while_, _for_

 Other varients of JavaScript _for_ loop:

 * _for .. of_ loop
 ```javascript 
 for (let value of array) {
   // do something with value
 }
 ```
 * _for .. in_ loop
 ```javascript 
 for (let property in object) {
   // do something with object property
 }
 ```

12. Logical short circuit: [tbd]

`obj1 && obj2` and `obj1 || obj2`


