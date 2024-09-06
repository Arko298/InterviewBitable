13392
## Array_2D
```
def performOps(A):
    m = len(A)
    n = len(A[0])
    B = []
    for i in xrange(len(A)):
        B.append([0] * n)
        for j in xrange(len(A[i])):
            B[i][n - 1 - j] = A[i][j]
    return B

Lets say performOps was called with A : [[1, 2, 3, 4], [5, 6, 7, 8], [9, 10, 11, 12]] .
What would be the output of the following call :

B = performOps(A)
for i in xrange(len(B)):
    for j in xrange(len(B[i])):
        print B[i][j]
```
Ans: ` 4 3 2 1 8 7 6 5 12 11 10 9`
<Br/>
Explanation: Focus on the `B[i][n - 1 - j] = A[i][j]` it mean we have to reverse the matrix according to the rows.

<Br/>

## Array_Bug
The code is given, there's a small bug fix it
The following code is supposed to rotate the array A by B positions.

So, for example,


```
A : [1 2 3 4 5 6]
B : 1
```


The output :

`[2 3 4 5 6 1] `
<Br/>
However, there is a small bug in the problem. Fix the bug and submit the problem.

```
class Solution:
    # @param a : list of integers
    # @param b : integer
    # @return a list of integers
    def rotateArray(self, a, b):
        ret = []
		
        for i in xrange(len(a)):
            ret.append(a[(i + b)])
        return ret

```
Just add ` %len(a)` in ` ret.append(a[(i+b)%len(a)])` this will rotate the array by the desired requirement
<Br />

## ARRAY_IMPL1
Predict the output
```
def performOps(A):
    blen = 2 * len(A)
    B = [0]*blen
    for i in xrange(len(A)):
        B[i] = A[i]
        B[i + len(A)] = A[(len(A) - i) % len(A)]
    return B

Lets say performOps was called with A : [5, 10, 2, 1].
What would be the output of the following call :

( NOTE : The output shoudl be written in the below provided text field , there should not be any ‘,’ between the numbers . For example: 1 2 3 4 )

B = performOps(A)
for i in xrange(len(B)):
    print B[i]
```
The output : ` 5 10 2 1 5 1 2 10`
<Br />
Just dry run the commands and boom..