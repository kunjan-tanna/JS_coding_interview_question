# JS_coding_interview_question

1. Write a function that returns the reverse of a string.
2. Write a function that returns the longest word in a sentence.
3. Write a function that checks whether a given string is a palindrome or not.
4. Write a function to remove the duplicate elements from an array.
5. Write a function that checks whether two strings are anagrams or not.
6. Write a function that returns the number of vowels in a string.
7. Write a function to find the largest number in an array.
8. Write a function to check if a given number is prime or not.
9. Write a function to calculate the factorial of a number.
10. Write a program to remove all whitespace characters from a string.
11. Write an program for sort an array of object
12. Write an program for fibonacci series up to n terms.
13. Write an program for showing the count for duplicate from string and return output object format

## Q1 => Function to Reverse a String

The following function `reverString` takes a string as input and returns its reverse.

### Code:
### Method 1: Using a Loop
```javascript
/**
 * Function to reverse a given string.
 * @param {string} str - The input string to be reversed.
 * @returns {string} - The reversed string.
 */
function reverString(str) {
    console.log(str);
    
    let newStr = "";
    for (let i = str.length - 1; i >= 0; i--) {
        newStr += str[i];
    }
    return newStr;
}

const finalVal = reverString("Happy");

console.log('finalVal', finalVal);  // Output: yppaH
```
### Method 1: Built-In Method
```javascript
/**
 * Function to reverse a given string using built-in methods.
 * @param {string} str - The input string to be reversed.
 * @returns {string} - The reversed string.
 */
function reverString(str) {
    return str.split("").reverse().join("");
}

const finalVal = reverString("Happy");

console.log('finalVal', finalVal);  // Output: yppaH
```

## Q2 => Function to longest word/string in a sentence
```javascript
/**
 * Function to find the longest word in a given sentence.
 * @param {string} str - The input sentence.
 * @returns {string} - The longest word in the sentence.
 */
function findLongestWord(str) {
    let splitStr = str.split(" ");
    let longestWord = 0;
    let strLong;
    
    console.log(splitStr);
    
    for (let i = 0; i < splitStr.length; i++) {
        if (splitStr[i].length > longestWord) {
            longestWord = splitStr[i].length;
            strLong = splitStr[i];
        }
    }
    return strLong;
}

const finalVal = findLongestWord("i want to be happy");

console.log('finalVal', finalVal);  // Output: happy
```
## Q3 => Function to check if the string is palindrome or not

Palindrome : Sequence of numbers, string or latters to read left to right and right to left compare the exact same word like nitin, madam etc..

### Method 1: ShortCut method
```javascript
/**
 * Function to check if a given string is a palindrome.
 * A palindrome is a word, phrase, number, or other sequence of characters that reads the same backward as forward.
 *
 * @param {string} string - The string to check for palindrome property.
 * @returns {boolean} - Returns true if the string is a palindrome, false otherwise.
 */
function checkPalindrome(string) {
    // Reverse the input string by splitting it into an array of characters, reversing the array, and joining it back into a string
    let revserStr = string.split("").reverse().join("");

    // Check if the original string is equal to the reversed string
    return string === revserStr;
}

// Call the function with a sample input
const value = checkPalindrome('nitin'); // 'nitin' is a palindrome
console.log(value); // Output: true


```
### Method 2: Offically using for loop
```javascript
/**
 * Function to check if a given string is a palindrome.
 * @param {string} string - The string to be checked.
 * @returns {string} - A message indicating whether the string is a palindrome or not.
 */
function checkPalindrome(string) {

    // Find the length of the string
    const len = string.length;

    // Loop through half of the string
    for (let i = 0; i < len / 2; i++) {

        // Check if the first and last characters of the string are the same
        if (string[i] !== string[len - 1 - i]) {
            return 'It is not a palindrome';
        }
    }
    return 'It is a palindrome';
}

// Call the function with an example string
const value = checkPalindrome('nitin'); // It is a palindrome, Nitin => it is not palindrome, Kunjan => it is not palindrome
```
## Q4 => Function to remove the duplicate elements from an array

### Method 1 : using Set() method
```javascript
let arr =  [1,2,3,4,2,3,6,7];

/**
 * Removes duplicate elements from an array.
 * 
 * @param {Array} arr - The array from which duplicates need to be removed.
 * @returns {Array} A new array with duplicates removed.
 */
function removeDuplicates(arr) {
    return [...new Set(arr)];
}

const finalVal = removeDuplicates(arr);
console.log(finalVal); //[1,2,3,4,6,7]
```

### Method 2 : using filter() method

```javascript

/**
 * Removes duplicate elements from an array.
 *
 * @param {Array} arr - The array from which duplicates will be removed.
 * @returns {Array} - A new array with duplicates removed.
 */
let arr = [1,2,3,4,5,2,3];
function removeDuplicates(arr) {
    return arr.filter((item, index) => arr.indexOf(item) === index);
}

const finalVal = removeDuplicates(arr);
console.log(finalVal); //[1,2,3,4,5]

```
### Method 3 : using indexOf() method

```javascript
/**
 * Removes duplicate elements from an array.
 * 
 * @param {number[]} arr - The array from which duplicates are to be removed.
 * @returns {number[]} A new array with duplicates removed.
 */
let arr = [1,2,3,4,2,3,6]
function removeDuplicates(arr) {
    let uniEle = []
    for(let i = 0; i < arr.length; i++) {
        if(uniEle.indexOf(arr[i]) == -1) {
            uniEle.push(arr[i])
        }
    }
    return uniEle
}

const finalVal = removeDuplicates(arr)
console.log(finalVal); //[ 1, 2, 3, 4, 6 ]

```
## Q5 => Function to checks whether two strings are anagrams or not. [IMP]

Anagrams : anagrams is word formed by rearranging the latter of another word.
examples : cheater => teacher, listen => slient

```javascript
/**
 * Checks if two strings are anagrams of each other.
 * 
 * An anagram is a word or phrase formed by rearranging the letters of a different word or phrase,
 * typically using all the original letters exactly once.
 * 
 * @param {string} str1 - The first string to compare.
 * @param {string} str2 - The second string to compare.
 * @returns {boolean} - Returns true if the strings are anagrams, false otherwise.
 */
function areAnagrams(str1, str2) {
    let firstStr = str1.split("").sort().join("");
    let secondStr = str2.split("").sort().join("");
    return firstStr === secondStr;
}

const finalVal = areAnagrams("cheater", "teacher");
console.log(finalVal); // Output: true

```
## Q6 => Function that returns the number of vowels in a string

vowels = a,e,i,o,u

```javascript
const vowels = ["a", "e", "i", "o", "u"]

/**
 * Counts the number of vowels in a given string.
 * 
 * @param {string} str - The string to count vowels in.
 * @returns {number} The number of vowels in the string.
 */
function countVowel(str) {
    // initialize count
    let count = 0;

    // loop through string to test if each character is a vowel
    for (let letter of str.toLowerCase()) {
        if (vowels.includes(letter)) {
            count++;
        }
    }

    // return number of vowels
    return count;
}

const result = countVowel("Hello World");

console.log(result); // Output: 3
```
## Q7 => Function to find the largest number in an array (IMP)

### Method 1 : using Math.max() Method

```javascript
/**
 * Finds the largest number in an array.
 *
 * @param {number[]} arr - An array of numbers.
 * @returns {number} The largest number in the array.
 */
function findLargeNumber(arr) {
    let largeNumber = Math.max(...arr);
    return largeNumber;
}

const finalVal = findLargeNumber([1, 2, 3, 4, 5]);
console.log(finalVal); // 5
```
### Method 2 : using for loop

```javascript
/**
 * Finds the largest number in an array.
 *
 * @param {number[]} arr - The array of numbers to search through.
 * @return {number} The largest number in the array.
 */
function findLargeNumber(arr) {
   let largeNumber = arr[0];
   for (let i = 1; i < arr.length; i++) {
       if (arr[i] > largeNumber) {
           largeNumber = arr[i];
       }
   }
   return largeNumber;
}

const finalVal = findLargeNumber([1, 2, 3, 9, 5]);
console.log(finalVal); // 9
```
## Q8 => Function to check if a given number is prime or not (IMP)

Prime : Prime numbers are numbers that have only 2 factors: 1 and themselves. For example, the first 5 prime numbers are 2, 3, 5, 7

```javascript
/**
 * Checks if a given number is a prime number.
 * 
 * @param {number} number - The number to be checked.
 * @returns {boolean} - Returns true if the number is prime, false otherwise.
 */
function isPrimeOrNot(number) {
    var isPrime = true;
    for(let i = 2; i < number; i++) {
        if (number % i == 0) {
            isPrime = false;
            break;
        }
    }
    return isPrime;
}

const finalVal = isPrimeOrNot(7);
console.log(finalVal); //true && if 10 => return false

```
## Q9 => Function to calculate the factorial of a number (IMP)

The factorial of a number is the product of all the numbers from 1 to that number. For example,

factorial of 5 is equal to 1 * 2 * 3 * 4 * 5 = 120.

```javascript
/**
 * Calculates the factorial of a given number.
 *
 * @param {number} number - The number to calculate the factorial of.
 * @returns {number} The factorial of the given number.
 */
function factorialNumber(number) {
    let factNo = 1;
    
    // If the number is 0, return 1 as 0! is 1
    if (number == 0) {
        return 1;
    }

    // Loop from 1 to the given number
    for (let i = 1; i <= number; i++) {
        factNo *= i;
    }

    return factNo;
}

const finalVal = factorialNumber(5);
console.log(finalVal); // 120
```
## Q10 => program to remove all whitespace characters from a string

```javascript
/**
 * Removes all white spaces from a given string.
 *
 * @param {string} str - The string from which white spaces should be removed.
 * @returns {string} - The string with all white spaces removed.
 */
function removeWhiteSpace(str) {
   return str.replace(/\s/g, '')
}

const finalVal = removeWhiteSpace("    Happy Kunjan");
console.log(finalVal); // HappyKunjan
```
## Q11 => Write an program for sort an array of object
### Method 1 : Acending order
```javascript

let employees = [
  { name: 'John', dob: 'Dec 15, 2007', score: 80 },
  { name: 'Ana', dob: 'Jan 15, 2009', score: 75 },
  { name: 'Zion', dob: 'Feb 15, 2011', score: 90 },
];

employees.sort((a,b)=>a.score - b.score)

console.log(employees) //ascending order
```
### Method 1 : Descending order
```javascript

let employees = [
  { name: 'John', dob: 'Dec 15, 2007', score: 80 },
  { name: 'Ana', dob: 'Jan 15, 2009', score: 75 },
  { name: 'Zion', dob: 'Feb 15, 2011', score: 90 },
];

employees.sort((a,b)=>b.score - a.score)

console.log(employees) //descending order

```
## Q12 => Write an program for fibonacci series up to n terms
```javascript

// program to generate fibonacci series up to n terms
function fibNo(number){
    let n1=0, n2=1, nextTerm;
    
    for(let i=1;i<=number;i++){
        nextTerm = n1+n2
        n1 = n2;
        n2 = nextTerm
        console.log(n2)
    }
     return n2;
}

const fibonacciNo = fibNo(8)
console.log('fibonacciNo',fibonacciNo)
```

## Q13 => Write an program for showing the count for duplicate from string and return output object format
```javascript
const checkCount = checkData('ELEPHANT')
console.log(checkCount)
function checkData(str){
    const spiltStr = str.split("")
   
    const newData = spiltStr.filter((item, index)=> spiltStr.indexOf(item) !== index)
     console.log('newData',newData)
    let count = 0;
    let formData = {}
     for(let latter of spiltStr)
     {
         
         if(newData.includes(latter))
         {
             
             count++;
             console.log(latter)
             formData[latter] = count
             //console.log(formData)
         }else{
             formData[latter] = 1
             //console.log(formData)
            // count += 1
         }
     }
     return formData
}
Output : { E: 2, L: 1, P: 1, H: 1, A: 1, N: 1, T: 1 }

```

