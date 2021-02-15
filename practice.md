# Practice Questions

1) How do you find the missing number in a given integer array of 1 to 100?


```
var missingNum = function(numArray){
    for(let i  = 1; i < 100; i++){
      if(numArray[i] != i) return i;
    }
    return -1; // if no number missing?
}; // Brute Force O(n) solution
```


```
var missingNum = function(numArray){
  let val = 0;



  return val;
};
```

2) How do you find the duplicate number on a given integer array?

```
var dupNum = function(numArray){
  let numSet = new Set();
  for(let i = 0; i < numArray.length; i++){
    if(numSet.has(numArray[i])) {
      numSet.add(numArray[i]); // if we haven't seen the current number yet, we add it to a Set
    } else{
      return numArray[i]; // if we have, we can return immediately
    }
  }
  return -1; //if the array has no duplicate values?
};
```

3) How do you find the largest and smallest number in an unsorted integer array?

```
var smallLarge = function(numArray){
  let low = numArray[0];
  let high = numArray[0];

  for(let i = 0; i < numArray.length; i++){
    let currNum = numArray[i];

    if(low > currNum) low = currNum;
    if(high < currNum) high = currNum;
  }

  return [low, high];
};
```

4) How do you find all pairs of an integer array whose sum is equal to a given number?

```
// assuming array is sorted

var sumPairs = function(numArray, target){
    let pairSet = new Set();
    for(let i = 0; i < numArray.length; i++){
      for(let j =  i + 1; j < numArray.length; j++){
        if(numArray[i] + numArray[j] > target) break;

        if(numArray[i] + numArray[j] == target){
          if(!pairSet.has([numArray[i], numArray[j]])){
            pairSet.add([[numArray[i]], numArray[j]]);
          }
        }
      }
    }
    return pairSet.keys();
}
```

5) How do you find duplicate numbers in an array if it contains multiple duplicates?

```
var dups = function(numArray){

  let result = [];
  let set = new Set();

  for(let i = 0; i < numArray.length; i++){
    if(!set.has(numArray[i])){
      result.push(numArray[i]);
    }else{
      set.add(numArray[i]);
    }
  }

  return result;
}

```

6) How is an integer array sorted in place using quicksort?
