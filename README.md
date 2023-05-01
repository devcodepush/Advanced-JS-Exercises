 # Hi! 👋

## 🚀 Advanced-JS-Exercises

Click on this [link](https://devcodepush.github.io/Advanced-JS-Exercises/) to see GitHub page

### Exercise - Adv JS 1 - Arrays in depth

##### Write a function called capitalize() that takes a string and uses .map to return the same string in all caps. 
###### ex: capitalize('whoop') => 'WHOOP' 
###### ex: capitalize('oh hey gurl') => "OH HEY GURL"

```javascript
function capitalize(string) {
    return string.toUpperCase().split('').map(char => char.toUpperCase()).join('');
}

console.log(capitalize('oh hey gurl'))
```


##### Now write a new function called swapCase() that takes a string of words and uses .map and function capitalize(string) to return a string where every other word is in all caps.

```javascript
const swapCase = function (string) {
    return string.split(" ").map((word, index) => (index % 2 == 0) ? word.toUpperCase() : word).join(" ");
}

console.log(swapCase('whoop'))
```


##### Write a function shiftLetters() that takes a string and uses .map to return an encoded string with each letter shifted down the alphabet by one. 
###### Hint: Use Look up the JS functions String.fromCharCode() and String.CharCodeAt() and see if you can use Ascii code to acomplish this.

```javascript
const shiftLetters = function (string) {
    return string.split('').map(letter => {
        let charCode = letter.charCodeAt(0)
        charCode += 1;
        letter = String.fromCharCode(charCode)
        return letter
    }).join('')
}

console.log(shiftLetters('abcxyz'))
```


##### Write a function counterLetters() that takes a string and returns an object representing the character count for each letter. Use .reduce to build this object. 

```javascript
function counterLetters(str) {
    return str.split('').reduce((acc, curr) => {
      if (/[a-zA-Z]/.test(curr)) {
        const letter = curr.toLowerCase();
        acc[letter] = acc[letter] ? acc[letter] + 1 : 1;
      }
      return acc;
    }, {});
  }

  console.log(counterLetters('abbcccddddeeeee'));
  ```
  

##### Write a function isPresent() that takes a string and a target, and returns true or false if the target is present in the string. Use .reduce to acomplish this. 

```javascript
function isPresent(str, target) {
    return str.split('').reduce((acc, curr) => {
      return acc || curr === target;
    }, false);
  }
  
  console.log(isPresent('abcd', 'b'));
  ```


### Exercises - Advanced JS 4 - spread/rest, destructuring

##### Write a function called squareAndSum that takes in any number of arguments, squares them, then sums all of the squares.

```javascript
function squareAndSum(...args) {
    return args.reduce((acc, curr) => {
      return acc + curr ** 2;
    }, 0);
  }

  console.log(squareAndSum(1, 2, 3, 4, 5, 6, 7, 8, 9, 10));
  ```
  

##### Write a function called combineTwoArrays that takes in two arrays as arguments, and returns a single array that combines both (using the spread operator).

```javascript
function combineTwoArrays(arr1, arr2) {
    return [...arr1, ...arr2];
  }

  console.log(combineTwoArrays([1, 2, 3], [4, 5, 6]));
```  

##### Write a function called onlyUniques that can take in any number of arguments, and returns an array of only the unique arguments

```javascript
function onlyUniques(...args) {
    return [...new Set(args)];
  }

  console.log(onlyUniques(1, 2, 3, 4, 5, 6, 7, 8, 9, 10));
  ```
