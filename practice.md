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

19) How do you print duplicate characters from a string?

```
var dupChars = function(string){
  let dupCharArray = [];
  let charCounterArray = [];

  for(let i = 0; i < 26; i++){
    charCounterArray.push(0);
  }

  for(let i = 0; i < string.length; i++){
    charCounterArray[string[i].charCodeAt(0)-97] += 1;
  }

  for(let i = 0; i < 26; i++){
    if(charCounterArray[i] > 1) dupCharArray.push(String.fromCharCode(i+97));
  }

  return dupCharArray;
};

```

20) How do you check if two strings are anagrams of each other?

```
var anagrams = function(string1, string2){
  return string1.split("").sort.join("") === string2.split("").sort().join("");
};
```

21) How do you print the first non-repeated character from a string?

```
var printUnique = function(string){
  let charMap = new Map();

  for(let i = 0; i < string.length; i++){
      if(!charMap.has(string[i])){
        charMap.set(string[i], 1);
      }else{
        charMap.set(string[i], charMap.get(string[i]) + 1);
      }
  }
  for(let i = 0; i < string.length; i++){
        if(charMap.get(string[i]) == 1) return string[i];
  }
};

```

22)How can a given string be reversed using recursion?

```
var reverseString = function(string){
  if(string.length == 0) return "";

  return string.slice(string.length-1) + reverseString(string.slice(0,string.length - 1));
}
```

23) How do you check if a string contains only digits?

```
var onlyDigits = function(string){

  for(let i = 0 ; i < string.length; i++){
      let currChar = string[i];

      if(currChar.charCodeAt(0) < 48 || currChar.charCodeAt(0) > 57) return false;
  }

  return true;
};
```

24) How do you count a number of vowels and consonants in a given string?

```
var vowelConCount = function(string){
  let vowels = ["a", "e", "i", "o", "u"];
  let vowelSet = new Set();

  for(let i = 0 ; i < vowels.length; i++){
    vowelSet.add(vowels[i]);
  }

  let vowelCount = 0;
  let consonantCount = 0;

  let lowerString = string.toLowerCase();

  for(let i = 0 ; i < string.length ; i++){
    if(vowelSet.has(lowerString[i])){
      vowelCount +=1;
    }else{
      consonantCount +=1;
    }
  }
  return [vowelCount, consonantCount];
}
```    
