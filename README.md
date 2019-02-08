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
