# Sorted Sort

Similar to bubble Sort, but instead of first placing large values into sorted position,
it places small values into sorted position.

move beginning to end
swap start and the smallest(min)

## Selection Sort Pseudocode

 - Store the first element as the smallest value you've seen so far.
 - Compare this item to the next item in the array until you find a smaller number.
 - If a smaller number is found, designate that smaller number to be the new "minimum" and continue until the end of the array.
 - If the "minimum" is not the value (index) you initially began with, swap the two values.
 - Repeat this with the next element until the array is sorted.

### Code by Claude
```typescript
function selectionSort(arr:number[]):number[]{
	 for (let i = 0; i < arr.length - 1; i++) {
        let minIndex = i;
        
        // Find the minimum element in the unsorted portion
        for (let j = i + 1; j < arr.length; j++) {
            if (arr[j] < arr[minIndex]) {
                minIndex = j;
            }
        }
        
        // Swap the found minimum element with the first element of unsorted portion
        if (minIndex !== i) {
            [arr[i], arr[minIndex]] = [arr[minIndex], arr[i]];
        }
    }
    
    return arr;
}

```

### Code From the Lecture
```typescript
function selectionSort(arr:number[]):number[]{
		const swap = (arr, idx1, idx2) => {
				[arr[idx1],arr[idx2]] = [arr[idx2],arr[idx1]];
        }
				
		for(let i = 0; i < arr.length-1; i++){
				let lowest = i;
				for(let j = i+1; j < arr.length; j++){
						if(arr[lowest] > arr[j]){
								lowest = j
                        }
                if( i !== lowest){
					swap(arr, i, lowest)
                }
				}
        }
		return arr;
}

```

## When to use 
when you want to minimize the number of swaps (concerned about writing to memory or so on)
