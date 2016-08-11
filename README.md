# Limesharp test

Fork this repo, commit changes after each task and send us the link to your repo (don't do a PR, just send us the link).
We will get back to you shortly. 
Languages accepted: js, php, python, ruby. 

### Task 1: 
Make this work (repeat 3 times the contents of an array):
```javascript
repeat([1,2,3]) //[1,2,3,1,2,3,1,2,3]
```
Your solution:

###### if we type in our console your function and repeat([1,2,3]) then the result should be [1,2,3,1,2,3,1,2,3] 

function repeat(Array $arrayToBeRepeated) {
    $repeatTimes = 3;
    echo "[";
    while ($repeatTimes) {
        $stringFormatOfArray = implode(',', $arrayToBeRepeated);
        echo $stringFormatOfArray;
        $repeatTimes--;
        if ($repeatTimes) {
            echo ",";
        }
    }
    echo "]".PHP_EOL;
}

### Task 2:
Make this work (no vowels, lowercase except the first letter):
```javascript
reformat("liMeSHArp DeveLoper TEST") //Lmshrp dvlpr tst
```
Your solution:

###### if we type in our console your function and reformat("liMeSHArp DeveLoper TEST") then the result should be Lmshrp dvlpr tst

function reformat($originString) {
    $vowels = ['a', 'e', 'i', 'o', 'u'];
    $resultString = $originString;
    $resultString = strtolower($resultString);
    $resultString = str_replace($vowels, '', $resultString);
    echo $resultString . PHP_EOL;
}


### Task 3 (optional, for bonus points):
Make this work (without using any built in functions, only a `for` loop, return the next binary number in a string or as an array)
```javascript
next_binary_number([1,0]) // [1,1]

// possible test cases:
// [1,0] => [1,1]
// [1,1] => [1,0,0]
// [1,1,0] => [1,1,1]
// .......
// [1,0,0,0,0,0,0,0,0,1] => [1,0,0,0,0,0,0,0,1,0]
```
Your solution:

###### if we type in our console your function and next_binary_number([1,0,0,0,0,0,0,0,0,1]) then the result should look like 1,0,0,0,0,0,0,0,1,0 (or as an array).

function next_binary_number(Array $arrayAsBinary) {
    $length = count($arrayAsBinary);
    $carry = 1;
    
    echo "[";
    for ($index = $length-1; $index >= 0; $index--) {
        $number = $arrayAsBinary[$index];
        $number = $number + $carry;
        $arrayAsBinary[$index] = $number%2;
        if ($number >= 2) {
            $carry = 1;
        } else {
            $carry = 0;
        }
    }
    
    if($carry){
        echo "1,";
    }
    
    $string = implode(",", $arrayAsBinary);
    echo $string . "]" .PHP_EOL;
}

###### If you get invited to the first interview read the What to expect.md file.
