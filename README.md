# Dsa-Questions-Solved

# JavaScript Utility Functions

This repository contains some commonly used JavaScript functions. Below are the examples with their descriptions.

---

## 1. Reverse Words in a String

javascript
let string = "Try programiz pro";
let result = "";
let word = "";

// Loop through each character in the string
for (let i = 0; i <= string.length; i++) {
    if (i === string.length || string[i] === " ") {
        for (let j = word.length - 1; j >= 0; j--) {
            result += word[j];
        }
        if (i !== string.length) {
            result += " ";
        }
        word = "";
    } else {
        word += string[i];
    }
}

console.log(result); 
 



Check anagram
function areAnagrams(str1, str2) {
    // Convert both strings to lowercase using toLowerCase()
    let cleanedStr1 = '';
    let cleanedStr2 = '';

    // Manually remove spaces and apply toLowerCase()
    for (let i = 0; i < str1.length; i++) {
        if (str1[i] !== ' ') {
            cleanedStr1 += str1[i].toLowerCase();
        }
    }

    for (let i = 0; i < str2.length; i++) {
        if (str2[i] !== ' ') {
            cleanedStr2 += str2[i].toLowerCase();
        }
    }

    // If the lengths don't match, they can't be anagrams
    if (cleanedStr1.length !== cleanedStr2.length) {
        return false;
    }

    // Create frequency counters for both strings
    let frequencyCounter1 = {};
    let frequencyCounter2 = {};

    for (let i = 0; i < cleanedStr1.length; i++) {
        let char = cleanedStr1[i];
        if (frequencyCounter1[char]) {
            frequencyCounter1[char]++;
        } else {
            frequencyCounter1[char] = 1;
        }
    }

    for (let i = 0; i < cleanedStr2.length; i++) {
        let char = cleanedStr2[i];
        if (frequencyCounter2[char]) {
            frequencyCounter2[char]++;
        } else {
            frequencyCounter2[char] = 1;
        }
    }

    // Compare frequency counters
    for (let char in frequencyCounter1) {
        if (frequencyCounter1[char] !== frequencyCounter2[char]) {
            return false;
        }
    }

    return true;
}

// Example usage:
let string1 = "Listen";
let string2 = "Silent";

if (areAnagrams(string1, string2)) {
    console.log(`${string1} and ${string2} are anagrams.`);
} else {
    console.log(`${string1} and ${string2} are not anagrams.`);
}

Second Largest
function findSecondLargest(arr) {
  if (arr.length < 2) {
    return null; // No second largest element if array has less than 2 elements
  }

  let largest = -Infinity;
  let secondLargest = -Infinity;

  for (let i = 0; i < arr.length; i++) {
    if (arr[i] > largest) {
      secondLargest = largest; // Update second largest to the previous largest
      largest = arr[i];        // Update largest to the current element
    } else if (arr[i] > secondLargest && arr[i] !== largest) {
      secondLargest = arr[i];   // Update second largest if current element is between largest and second largest
    }
  }

  return secondLargest === -Infinity ? null : secondLargest;
}

// Example usage:
const arr = [10, 5, 20, 20, 8];
console.log(findSecondLargest(arr)); // Output: 10


// merge two sorted arrays 
const arr = [1,2,4,8,9]
const arr2 = [3,5,6,10]

const arr3=[]

  for (let i=0; i<=arr.length-1; i++){
        arr3.push(arr[i])
  }
  
   for (let i=0; i<=arr2.length-1; i++){
        arr3.push(arr2[i])
  }

console.log(arr3)

//  missingNumber In  an  array

function findMissingNumber(arr, n) {
  // Calculate the expected sum of numbers from 1 to n
  const expectedSum = (n * (n + 1)) / 2;

  // Calculate the actual sum of the array using a loop
  let actualSum = 0;
  for (let i = 0; i < arr.length; i++) {
    actualSum += arr[i];
  }

  // The missing number is the difference between expectedSum and actualSum
  return expectedSum - actualSum;
}

// Example usage:
const arr = [1, 2, 4, 5, 6];  // Missing number is 3
const n = 6; // As array should have numbers from 1 to 6
console.log(findMissingNumber(arr, n)); // Output: 3

   // Two Sum
function findPairsWithSum(arr, targetSum) {
  const pairs = [];
  const seen = {}; // Object to store numbers we have already encountered

  for (let i = 0; i < arr.length; i++) {
    const complement = targetSum - arr[i]; // Find the complement that would sum to targetSum

    if (seen[complement]) {
      pairs.push([arr[i], complement]); // If complement is in the object, add the pair
    }

    seen[arr[i]] = true; // Mark the current number as seen
  }

  return pairs;
}

// Example usage:
const arr = [2, 7, 4, 5, 3, 1, 9, 6];
const targetSum = 10;
console.log(findPairsWithSum(arr, targetSum));
// Output: [ [ 7, 3 ], [ 6, 4 ], [ 9, 1 ] ]

intersection 
function findIntersection(arr1, arr2) {
  const map = {}; // Object to store elements of the first array
  const intersection = [];

  // Store elements of the first array in the object
  for (let i = 0; i < arr1.length; i++) {
    map[arr1[i]] = true; // Mark the element as seen
  }

  // Check for common elements in the second array
  for (let i = 0; i < arr2.length; i++) {
    if (map[arr2[i]]) {
      intersection.push(arr2[i]); // If found in the object, add to result
      map[arr2[i]] = false; // Ensure we don't add duplicates
    }
  }

  return intersection;
}

// Example usage:
const arrayA = [1, 2, 2, 3, 4];
const arrayB = [2, 3, 5];
console.log(findIntersection(arrayA, arrayB)); // Output: [2, 3]


•  Remove Duplicates from an Array:
•	Write a function to remove duplicates from an unsorted array.
Example:
js
Copy code
function removeDuplicates(arr) {
  return [...new Set(arr)];
}
•  Find the Maximum and Minimum in an Array:
•	Write a function to find the maximum and minimum elements in an array without using built-in functions.
•  Find the Second Largest Element in an Array:
•	Write a function to find the second largest element in an array.
•  Merge Two Sorted Arrays:
•	Write a function to merge two sorted arrays into a single sorted array.
•  Find the Missing Number in an Array:
•	Given an array of size n-1 containing numbers from 1 to n, find the missing number.
•  Find All Pairs with a Given Sum:
•	Write a function to find all pairs in an array whose sum equals a given number.
•  Rotate an Array by k Positions:
•	Write a function to rotate an array to the right by k positions.
•  Check if Two Arrays are Equal:
•	Write a function to check if two arrays are equal, considering both content and order.
•  Move Zeros to the End of the Array:
•	Write a function to move all zeros in an array to the end while maintaining the relative order of other elements.
•  Find the Intersection of Two Arrays:
•	Write a function to find the intersection of two arrays (common elements between both arrays).


const string = "agahjak hakalkl";
let result = '';
let capitalizeNext = true; // Flag to determine when to capitalize

for (let i = 0; i < string.length; i++) {
  const char = string[i];

  if (capitalizeNext && char !== ' ') {
    result += char.toUpperCase();  // Capitalize the first letter of each word
    capitalizeNext = false;        // Set flag to false after capitalization
  } else {
    result += char;                // Append the character as is
  }

  if (char === ' ') {
    capitalizeNext = true;         // Set flag to true to capitalize next word
  }
}

console.log(result);  // Output: "Agahjak Hakalkl"


## Find single Number in Array
function singleNumber(nums: number[]): number {
     const numbers : {[key:string]: number} = {}
       for (let i=0; i<nums.length; i++){
         // this line cheks if the number exists in the then we will take like 
//          hash[num] checks if the number num exists in the hash:
// If hash[num] exists, add 1 to its value.
// If hash[num] doesn’t exist, use 0 as the default value (hash[num] || 0) and initialize it with 1.
           numbers[nums[i]] = (numbers[nums[i]] || 0) + 1
       }

       for ( let num in numbers ){
          if(numbers[num] === 1){
            return parseInt(num)
          }
       }
       
};

//  Longest subarray with given sum K(positives)

lenOfLongestSubarr(arr, k) {
      const sumMap = {};
    let maxLength = 0;
    let currSum = 0;

    for (let i = 0; i < arr.length; i++) {
        currSum += arr[i];

        // If current sum is exactly k, update max length
        if (currSum === k) {
            maxLength = i + 1;
        }

        // Check if the complement exists in the map
        const complement = currSum - k;
        if (complement in sumMap) {
            maxLength = Math.max(maxLength, i - sumMap[complement]);
        }

        // Only update map if current sum not already present
        // This ensures we keep the first (leftmost) occurrence
        if (!(currSum in sumMap)) {
            sumMap[currSum] = i;
        }
    }
    
    return maxLength;   
    }

 ## Sort an array of 0's 1's and 2's

function sortColors(nums: number[]): void {
    // `low`: Tracks the boundary for 0s (red)
    // `mid`: Tracks the current element being processed
    // `high`: Tracks the boundary for 2s (blue)
    let low = 0, mid = 0, high = nums.length - 1;

    // Process elements until `mid` crosses `high`
    while (mid <= high) {
        if (nums[mid] === 0) {
            // If the current element is 0 (red):
            // Swap it with the element at `low` and move `low` and `mid` forward
            [nums[low], nums[mid]] = [nums[mid], nums[low]];
            low++;
            mid++;
        } else if (nums[mid] === 1) {
            // If the current element is 1 (white):
            // No swap needed; just move `mid` forward
            mid++;
        } else {
            // If the current element is 2 (blue):
            // Swap it with the element at `high` and move `high` backward
            [nums[mid], nums[high]] = [nums[high], nums[mid]];
            high--;
        }
    }
}


## Binary Search  Binary Search to find X in sorted array
function search(nums: number[], target: number): number {
      let low =0,  high= nums.length -1 ; 

      while (low<=high) {
      let mid = Math.floor((low + high)/2)
      
         if( nums[mid] === target) return mid ; 
         else if (target > nums[mid]) {
            low = mid+1
         }
         else {
            high = mid-1
         }

      }
      return -1
};


