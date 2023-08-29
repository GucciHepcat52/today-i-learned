# Time Complexity

## What is Time Complexity?

Time complexity quantifies the amount of time taken by an algorithm to run as a function of the length of the input. The time needed for the completion of the algorithm.

> Note: Time complexity does not refer to the actual execution time of the machine on which the algorithm is running.

- To estimate time complexity, we need to consider the cost of each fundamental instruction and the number of times the instruction is executed.

- **_Constant time (c)_** , is taken to execute one operation, and then the total operations for an input length on **_N_** are calculated.

### Types of Time Complexities

- **_Constant Time Complexity - 0(1)_**

  - Algorithms with constant time complexity take the same amount of time regardless of input size

  ```
   // Example: Accessing an element in an array by index

   function getElement(arr, index) {
       return arr[index];
   }
  ```

- **_Linear Time Complexity - 0(n)_**

  - Algorithms with linear time complexity have their running time proportional to the size of the input

  ```
  // Example: Summing all elements in an array

  function sumElements(arr) {
      let total = 0;

      for (const num of arr) {
          total += num
      }

      return total;
  }
  ```

- **_Quadratic Time Complexity - 0(n^2)_**

  - Algorithms with quadratic time complexity have running times that are proportional to the square of the input size

  ```
  // Example: Bubble Sort

  function bubbleSort(arr) {
      const n = arr.length;

      for (let i = 0; i < n; i++) {
          for (let j = 0; j < n - i - 1; j++) {
              if (arr[j] > arr[j + 1]) {
                  [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]];
              }
          }
      }
  }
  ```

- **_Logarithmic Time Complexity - 0(log n)_**

  - Algorithms with logarithmic time complexity halve the input size with each step

  ```
  // Example: Binary Search

  function binarySearch(arr, target) {
    let low = 0;
    let high = arr.length - 1;

    while (low <= high) {
        const mid = Math.floor((low + high) / 2);
        if (arr[mid] === target) {
            return mid;
        } else if (arr[mid] < target) {
            low = mid + 1;
        } else  {
            high = mid - 1;
        }
    }

    return -1;
  }
  ```

- **_Linearithmic Time Complexity - 0(n log n)_**

  - This complexity is often seen in efficient sorting algorithms like Merge Sort and Heap Sort

  ```
    // Example: Merge Sort

    function mergeSort(arr) {
      if (arr.length > 1) {
        const mid = Math.floor(arr.length / 2);
        const leftHalf = arr.slice(0, mid);
        const rightHalf = arr.slice(mid);

        mergeSort(leftHalf);
        mergeSort(rightHalf);

        let i = j = k = 0;

        while (i < leftHalf.length && j < rightHalf.length) {
            if (leftHalf[i] < rightHalf[j]) {
                arr[k] = leftHalf[i];
                i++;
            } else {
                arr[k] = rightHalf[j];
                j++;
            }
            k++;
          }

        while (i < leftHalf.length) {
            arr[k] = leftHalf[i];
            i++;
            k++;
          }

        while (j < rightHalf.length) {
            arr[k] = rightHalf[j];
            j++;
            k++;
          }
      }
    }

  ```
