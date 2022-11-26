# Bubble sort

**Bubble Sort** is the most straightforward sorting algorithm that works by repeatedly swapping the adjacent elements if they are in the wrong order. This algorithm is unsuitable for large data sets as its average and worst-case time complexity is relatively high. Most learners consider that bubble sorting is easy than other sorting algorithms. 

**Characteristics of bubble short:  **
- It is the very simplest sorting.
- Starting from the first index, compare the first and the second elements.
- If the first element is greater than the second element, they are swapped.
- Not suitable for large data sets.
- Worst time complexity O(n²).
- Auxiliary space O(1).
- Bubble sort takes minimum time (Order of n) when elements are already sorted.
- The bubble sort algorithm is stable.

How does Bubble Sort Work?

```
Input: arr[] = {-2, 45, 0, 11, -9}
```

<strong>First Iteration (Compare and Swap):</strong>

```
- Bubble sort starts with the very first two elements, comparing them to check which one is greater.
- ( -2, 45, 0, 11, -9 ) –> ( -2, 45, 0, 11, -9 ), Here, nothing will be swapped in the first iteration.
- ( -2, 45, 0, 11, -9 ) –> ( -2, 0, 45, 11, -9 ), Here, the algorithm compares the second two elements, and swaps since 45 > 0.
- ( -2, 0, 45, 11, -9 ) –> ( -2, 0, 11, 45, -9 ), Here, the algorithm compares the third two elements, and swaps since 45 > 11.
- ( -2, 0, 11, 45, -9 ) –> ( -2, 0, 11, -9, 45 ), Here, the algorithm compares the fourth two elements, and swaps since 45 > -9.
```

<strong>Second Iteration:</strong> The same process goes on for the remaining iterations. After each iteration, the largest element among the unsorted elements is placed at the end.

```
- ( -2, 0, 11, -9, 45 ) –> ( -2, 0, 11, -9, 45 ), Here, nothing will be swapped in the first iteration because of 0 > -2.
- ( -2, 0, 11, -9, 45 ) –> ( -2, 0, 11, -9, 45 ), Here, nothing will be swapped in the second iteration because 11 > 0.
- ( -2, 0, 11, -9, 45 ) –> ( -2, 0, -9, 11, 45 ), Here, the algorithm compares the third two elements and swaps since 11 > -9.
```

<strong>Remaining Iteration:</strong>

```
- ( -2, 0, -9, 11, 45 ) –> ( -2, 0, -9, 11, 45 ), Here, nothing will be swapped in the first iteration because 0 > -2.
- ( -2, 0, -9, 11, 45 ) –> ( -2, -9, 0, 11, 45 ), Here, the algorithm compares the second two elements and swaps since 0 > -9.
```

<strong>Another Remaining Iteration:</strong>

```
- ( -2, -9, 0, 11, 45 ) –> ( -9, -2, 0, 11, 45 ), Here, the algorithm compares the first two elements, and swaps since -2 > -9.
```

The array is sorted when all the unsorted elements are placed at their correct positions and the final array will look like: `( -9, -2, 0, 11, 45 )`

Implementation: follow the below steps to sort a given unsorted data sets.

- Run a nested for loop to traverse the input array using two variables i and j, such that 0 ≤ i < n-1 and 0 ≤ j < n-i-1.
- If dataSets[j] is greater than dataSets[j+1] then swap these adjacent elements, else move on.

Below is the implementation of the above approach using JavaScript: 

```
function swapValue(itemContainer, firstItem, secondItem)
{
	var tempItem = itemContainer[firstItem];
	itemContainer[firstItem] = itemContainer[secondItem];
	itemContainer[secondItem] = tempItem;
}

function bubbleSort( itemContainer, itemLength )
{
    var firstIterator, secondIterator;
    for (firstIterator = 0; firstIterator < itemLength-1; firstIterator++)
    {
        for (secondIterator = 0; secondIterator < itemLength-firstIterator-1; secondIterator++)
        {
            if (itemContainer[secondIterator] > itemContainer[secondIterator+1])
            {
                swapValue(itemContainer,secondIterator,secondIterator+1);
            }
        }

    }
}

/* Function to print an array */
function printItems(itemContainer, size)
{
	var iterator;
	for (iterator=0; iterator < size; iterator++)
		document.write(itemContainer[iterator]+ " ");
	document.write("\n");
}

// Driver program to test above functions
var targetItems = [5, 1, 4, 2, 8];
var targetLength = 5;
document.write("UnSorted array: \n");
printItems(targetItems, targetLength);

bubbleSort(targetItems, targetLength);
document.write("Sorted array: \n");
printItems(targetItems, targetLength);
```

The time complexity is O(n²). Because the iteration will run O(n²) that means the iteration will check till the last item of the given data sets. 

**Optimized Implementation of Bubble Sort: **

```

// An optimized version of Bubble Sort
function bubbleSort(itemContainer, itemLength)
{
    var firstIterator, secondIterator, tempItem;
    var swapped;
    for (firstIterator = 0; firstIterator < itemLength - 1; firstIterator++)
    {
        swapped = false;
        for (secondIterator = 0; secondIterator < itemLength - firstIterator - 1; secondIterator++)
        {
            if (itemContainer[secondIterator] > itemContainer[secondIterator + 1])
            {
                // swap itemContainer[secondIterator] and itemContainer[secondIterator+1]
                tempItem = itemContainer[secondIterator];
                itemContainer[secondIterator] = itemContainer[secondIterator + 1];
                itemContainer[secondIterator + 1] = tempItem;
                swapped = true;
            }
        }

        // IF no two elements were
        // swapped by inner loop, then break
        if (swapped == false)
            break;
    }
}

// Function to print an array
function printItems(itemContainer, size)
{
    var iterator;
    for (iterator = 0; iterator < size; iterator++)
        document.write(itemContainer[iterator] + " ");
    document.writeln();
}

// Driver program
var targetItems = [ 64, 34, 25, 12, 22, 11, 90 ];
var targetLength = targetItems.length;
bubbleSort(targetItems, targetLength);
document.write("Sorted array: ");
printItems(targetItems, targetLength);
```

**Time Complexities**

  **Worst Case Complexity:** O(n2)
  If we want to sort in ascending order and the array is in descending order then the worst case occurs.
  
  **Best Case Complexity:** O(n)
  If the array is already sorted, then there is no need for sorting.

**Average Case Complexity:** O(n2)
  It occurs when the elements of the array are in jumbled order (neither ascending nor descending).

**Space Complexity**
  Space complexity is O(1) because an extra variable is used for swapping.
  In the optimized bubble sort algorithm, two extra variables are used. Hence, the space complexity will be O(2).

**Where should we use bubble sort?** 
- Complexity does not matter.
- Small sets of data.
- Short and simple code is preferred.

