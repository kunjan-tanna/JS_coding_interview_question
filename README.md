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
