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

### Method 1 : using filter() method

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
### Method 2 : using indexOf() method

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
