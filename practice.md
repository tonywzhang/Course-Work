# Practice Questions

1) How do you find the missing number in a given integer array of 1 to 100?

Questions to ask:

Can we assume the array is sorted?

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
