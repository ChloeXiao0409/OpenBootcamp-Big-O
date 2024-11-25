# OpenBootcamp-Big-O Answer
## 1. What is the Big O for this?
Determine the Big O for the following algorithm: You are sitting in a room with 15 people. You want to find a playmate for your dog, preferably of the same breed. So you want to know if anyone out of the 15 people have the same breed as your dog. You stand up and yell out, who here has a golden retriever and would like to be a playdate for my golden. Someone yells - "I do, be happy to bring him over"
### O(1) - because it will always someone just reply, cost constant time
Determine the Big O for the following algorithm: You are sitting in a room with 15 people. You want to find a playmate for your dog who is of the same breed. So you want to know if anyone out of the 15 people have the same breed as your dog. You start with the first person and ask him if he has a golden retriever. He says no, then you ask the next person, and the next, and the next until you find someone who has a golden or there is no one else to ask.
### O(n) - because it will ask people one by one cost linear time

## 2. Even or odd
    function isEven(value) {
        if (value % 2 === 0) {
            return true;
        }
        else {
            return false;
        }
    }﻿﻿
### O(1) - because comparison only cost constant time to compare

## 3. Are you here?
    function areYouHere(arr1, arr2) {
        for (let i = 0; i < arr1.length; i++) {    ----> O(n)
            const el1 = arr1[i];
            for (let j = 0; j < arr2.length; j++) {  ----> O(n)
                const el2 = arr2[j];
                if (el1 === el2) return true;
            }
        }
        return false;
    }
### O(n) * O(n) = O(n^2), exponential time

## 4. Doubler
    function doubleArrayValues(array) {
        for (let i = 0; i < array.length; i++) {  ----> O(n)
            array[i] *= 2;
        }
        return array;
    }
### O(n) - because for each iteration it do one multiplication

## 5. Naive search
    function naiveSearch(array, item) {
        for (let i = 0; i < array.length; i++) {
            if (array[i] === item) {
                return i;
            }
        }
    }
### O(n) - because for each iteration it make a comparing

## 6. Creating pairs
    function createPairs(arr) {
        for (let i = 0; i < arr.length; i++) {    ----> O(n)
            for(let j = i + 1; j < arr.length; j++) {  ----> O(n)
                console.log(arr[i] + ", " +  arr[j] );
            }
        }
    }
### O(n) * O(n) = O(n^2), exponential time

## 7. Compute the sequence
    function compute(num) {
        let result = [];
        for (let i = 1; i <= num; i++) {
    
            if (i === 1) {
                result.push(0);
            }
            else if (i === 2) {
                result.push(1);
            }
            else {
                result.push(result[i - 2] + result[i - 3]);
            }
        }
        return result;
    }
### O(n) - because other operations all constant time, but one for loop

## 8. An efficient search
    function efficientSearch(array, item) {
        let minIndex = 0;
        let maxIndex = array.length - 1;
        let currentIndex;
        let currentElement;
    
        while (minIndex <= maxIndex) {
            currentIndex = Math.floor((minIndex + maxIndex) / 2);
            currentElement = array[currentIndex];
    
            if (currentElement < item) {
                minIndex = currentIndex + 1;
            }
            else if (currentElement > item) {
                maxIndex = currentIndex - 1;
            }
            else {
                return currentIndex;
            }
        }
        return -1;
    }
### O(logn) - this is sorted and always compare with the mid, binary search

## 9. Random element
    function findRandomElement(arr) {
        return arr[Math.floor(Math.random() * arr.length)];
    }﻿﻿
### O(1) - because these are all constant time operations

## 10. What Am I?
    function isWhat(n) {
        if (n < 2 || n % 1 !== 0) {
            return false;
        }
        for (let i = 2; i < n; ++i) {
            if (n % i === 0) return false;
        }
        return true;
    }﻿﻿
### this algorothm is finding a prime number, it cost O(n) because only one loop
