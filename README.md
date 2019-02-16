# HackerRank

### Simple Array Sum

```javascript
function simpleArraySum(ar) {
    var sum = 0;
    for (var i = 0; i < ar.length; i++) {
        sum += ar[i];
    }
    return sum;
}
```

### Staircase

```javascript
function staircase(n) {
    for (let i = 1; i <= n; i++){
        console.log(' '.repeat(n - i) + '#'.repeat(i))
    }
}
```

### Diagonal Difference

visual representation

```javascript
arr [0][0] arr [0][1] arr[0][2] arr[0][3]
arr [1][0] arr [1][1] arr [1][2] arr[1][3]
arr [2][0] arr [2][1] arr [2][2] arr[2][3]
arr [3][0] arr [3][1] arr [3][2] arr[3][3]
|(arr[0][0] + arr [1][1] + arr [2][2] + arr [3][3]) - (arr[3][0] + arr[2][1] + arr [1][2] + arr[0][3])| 
```

```javascript
function diagonalDiff (arr) {
    let n = arr.length
    let left = 0
    let right = 0
    for (let i = 0; i < n; i++) {
       left += arr [i][i];
       right += arr [n-1-i][i]
    }
    return Math.abs(left+right)
} 
```

### Plus Minus

```javascript
function plusMinus(arr) {
    let n = arr.length;
    
    let posCount = 0
    let negCount = 0
    let nilCount = 0
    for ( let i=0; i < n; i++){
        if (arr[i] > 0){
            posCount++
        }
        if (arr[i] < 0){
            negCount++
        }
        if (arr[i] === 0){
            nilCount++
        }
    }
    console.log((posCount / n).toFixed(6))
    console.log((negCount / n).toFixed(6))
    console.log((nilCount / n).toFixed(6))
}
```

### A Very Big Sum 

```javascript
function aVeryBigSum(ar) {
    let total = ar.reduce((accumulator, currentValue) => accumulator + currentValue, 0);    
    return total;
}
```

### Birthday Candles

```javascript
function birthdayCakeCandles(ar) {
    let count = 0;
    let max = Math.max(...ar)
    for (let i = 0; i < ar.length; i++){
        if ( ar[i] === max ){
            count++
        }
    }
    return count
}
```

### Mini-Max Sum

```javascript
function miniMaxSum(arr) {
    let min = Math.min(...arr)
    let max = Math.max(...arr)
    let sum = arr.reduce((accumulator, currentValue) => accumulator + currentValue, 0)
    console.log(sum-max, sum-min)
}
```

### Compare the Triplets

```javascript
function compareTriplets(a, b) {
    let outputA = 0;
    let outputB = 0;
    for (let i=0; i < a.length; i++){
        if (a[i] < b[i]){
            outputB++
        } else if (a[i] > b[i]) {
            outputA++
        }
    }
    
    let output = [outputA, outputB]
    return output
}
```

### Grading Students

```javascript
function gradingStudents(grades) {
    return grades.map(grade => {
        if(grade < 38 || grade % 5 < 3) {
            return grade;
        } else if (grade % 5 >= 3){
            return (grade + (5 - grade % 5))
        } 
    }
}
```

### Apple & Orange

```javascript
function countApplesAndOranges(s, t, a, b, apples, oranges) {

    let appleOutput = 0;
    let orangeOutput = 0;

    let apple = apples.map(apples => apples + a);
    let orange = oranges.map(oranges => oranges + b);

    apple.forEach(apple => {
        if (apple >= s && apple <= t) {
            appleOutput++;
        }
    });
    
    orange.forEach(orange => {
        if (orange >= s && orange <= t) {
            orangeOutput++;
        }
    });
    
    console.log(appleOutput);
    console.log(orangeOutput);
}
```

### Kangaroo

```javascript
function kangaroo(x1, v1, x2, v2) {
    if (v1 < v2)
        return "NO";
    else {
        if ((v1 != v2) && ((x2 - x1) % (v1 - v2)) === 0)
            return "YES";
        else
            return "NO";
    }
}
```

### Breaking the Records

```javascript
function breakingRecords(scores) {
    let countHigh = 0;
    let countLow = 0;
    let min = scores[0];
    let max = scores [0];
    for (let i=1; i < scores.length; i++){
        
        if (scores[i] < min){
            min = scores[i];
            countLow++;
        }
        if (scores[i] > max){
            max = scores[i];
            countHigh++;
        }
    }
    return [countHigh, countLow]
}
```

### Migratory Birds

```javascript
function migratoryBirds(arr) {
    let count = {}
    arr.forEach(i => {count[i] = (count[i]||0)+1})
    return Object.keys(count).reduce((a,b) => count[a] < count[b] ? b : a)
}
```

### Bon Appétit

```javascript
function bonAppetit(bill, k, b) {
    let cost = b - ((bill.reduce((s, n) => s + n, 0) - bill[k]) / 2);
    console.log((cost === 0) ? "Bon Appetit" : cost )
}
```

### Divisible Sum Pairs

```javascript
function divisibleSumPairs(n, k, ar) {
    let count = 0;
    for (let i = 0; i < n; i++) {
        for (let j = i+1; j < n; j++) {
            if ((ar[i] + ar [j]) % k === 0) {
                count++;
            }
        }
    }
    return count;
}
```

### Cats and a Mouse

```javascript
function catAndMouse( x, y, z) {
        let temp = Math.abs(z-y) - Math.abs(z-x);
        if ( temp > 0) {
            return “Cat A”;
        } else if ( temp < 0) {
            return “Cat B”;
        } else if( temp == 0) {
            return “Mouse C”;
        }
}
```

### Hurdle Race

```javascript
function hurdleRace(k, height) {
    let dose = Math.max(...height) - k;
    if (dose < 0) return 0;
    else return dose;
}
```
