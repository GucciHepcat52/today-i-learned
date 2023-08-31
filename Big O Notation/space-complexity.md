# Space Complexity

## What is Space Complexity?

Space complexity is the amount of memory required by the algorithm to solve a given problem.

- This type of complexity quantifies the amount of space taken by an algorithm to run as a function of the length of the input.

- It is the amount of memory needed for the completion of an algorithm.

- To estimate the memory requirement, we need to focus on two parts:
  1. **A fixed part**: It is independent of the input size. It includes memory for instructions (code), constants, variables, etc.
  2. **A variable part**: It is dependent on the input size. It includes memory for recursion stack, referenced variables, etc.

### Types of Space Complexities

- **_Constant Space Complexity - 0(1)_**

  - Algorithms with constant space complexity use a fixed amount of memory regardless of the input size

  ```
   // Example: Finding the maximum element in an array

   function findMaxElement(arr) {
    let max = arr[0];

    for (const num of arr) {
        if (num > max) {
            max = num;
        }
    }

    return max;
   }
  ```

- **_Linear Space Complexity - 0(n)_**

  - Algorithms with linear space complexity use memory that's directly proportional to the size of the input

  ```
  // Example: Copying an array

  function copyArray(arr) {
    const newArr = [];

    for (const num of arr) {
        newArr.push(num);
    }

    return newArr;
  }
  ```

- **_Quadratic Space Complexity - 0(n^2)_**

  - Algorithms with quadratic space complexity have memory usage proportional to the square of the input size

  ```
  // Example: Generating all pairs of elements from two arrays

  function generatePairs(arr1, arr2) {
      const pairs = [];

      for (const num1 of arr1) {
          for (const num2 of arr2) {
              pairs.push([num1, num2]);
          }
      }

      return pairs;
  }
  ```

- **_Logarithmic Space Complexity - 0(log n)_**

  - Algorithms with logarithmic space complexity often involve recursive approaches that divide the problem into smaller parts

  ```
  // Example: Binary search using recursion

  function binarySearch(arr, target, low = 0, high = arr.length - 1) {
      if (low > high) {
        return -1;
      }
      const mid = Math.floor((low + high) / 2);
      if (arr[mid] === target) {
        return mid;
      } else if (arr[mid] < target) {
        return binarySearch(arr, target, mid + 1, high);
      } else {
        return binarySearch(arr, target, low, mid - 1);
      }
  }

  ```

- **_Linearithmic Space Complexity - 0(n log n)_**

  - This complexity is often seen in sorting algorithms like Merge Sort

  ```
  // Example: Merge Sort using recursion

  function mergeSort(arr) {
    if (arr.length <= 1) {
        return arr;
    }
    const mid = Math.floor(arr.length / 2);
    const leftHalf = arr.slice(0, mid);
    const rightHalf = arr.slice(mid);
    return merge(mergeSort(leftHalf), mergeSort(rightHalf));
  }

  function merge(left, right) {
    const result = [];
    let leftIndex = 0;
    let rightIndex = 0;
    while (leftIndex < left.length && rightIndex < right.length) {
        if (left[leftIndex] < right[rightIndex]) {
            result.push(left[leftIndex]);
            leftIndex++;
        } else {
            result.push(right[rightIndex]);
            rightIndex++;
        }
    }
    return result.concat(left.slice(leftIndex)).concat(right.slice(rightIndex));
  }

  ```
