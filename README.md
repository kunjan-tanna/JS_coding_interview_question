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


