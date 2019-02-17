***Matrix multiplication***     

A = [m * N] B = [L * K]

AB is Compatible for multiplication if

N == L  and after multiplication 

AB = m * L

AB != BA in all case.

Eg ; A = 1 2
         3 4

     B = 5 6
         7 8

C = 1*5 + 2*7   1*6 + 2*8
    3*5 + 4*7   3*6 + 4*8

Algorithm for multiplication

for(int i =0; i< n; i++){
  for(int j =0; j < n; i++) {
      C[i][j] = 0;
      for(int k=0; k <n; k++){
          C[i][j] += A[i][k] * B[k][j];
      }
  }
}

Time complexity is O(n^3);

Multiplication of Two matrix in term of 2 like 4*4, 8*8 etc
we can use divide and conquer methods.

break the matrix in 2*2 and write the formula
like C11 = A11 * B11 + A12 * B12;

and call recursivly like below

Algorithm MM(A, B, n){
    if(n < =2){
        use formula 
    }
    else {
      mid = n/2;
      MM(A1,b1, n/2) + MM(a2, b2, n/2)
      .....
    }
}

In this case also performance is O(n^3)

Strassen's gave formula to reduce some performnace but still time complexity is O(n^2.41)


***Optimal solutions finding***

1. Greedy algoritm
2. Dyanmic algorithm
3. bound and branching



***Greedy Algorithm***

It takes each input and check feasiblity and then add in the solution list.
In this case we test all the given input and find the best solutions on the slection basis.


*** Rules of magic square ***

matrix of size n is x = magic number is n(n^2+1)/2

by row, column, diagonla all sum sholud be same ie magic constant x.


rules to determine position of each number 

1.  1 stores at (n/2, n-1);
2.  next number stores at i-1, j+1 and 
        if i become -1 then reset to n-1
        if j is n then reset to 0
3. if at (i,j) number exist then (i+1, j-2)
4. if i, j position is (-1, n) => (0, n-2)