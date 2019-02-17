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
<<<<<<< HEAD


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
=======
Problem solve in stages and if solution is feasible add into the solution. It make greedy choice at stage.
This may not provide the best solution.
*It follow best method. without trying each input also we can find best solution.*

***Dynamic Programming***
- Time consuming, but it break the problem into sub problem and find the optimal solution.

***Difference between Greedy and Dynamic Programming ***
For example, let's say that you have to get from point A to point B as fast as possible, in a given city, during rush hour. A dynamic programming algorithm will look into the entire traffic report, looking into all possible combinations of roads you might take, and will only then tell you which way is the fastest. Of course, you might have to wait for a while until the algorithm finishes, and only then can you start driving. The path you will take will be the fastest one (assuming that nothing changed in the external environment).

On the other hand, a greedy algorithm will start you driving immediately and will pick the road that looks the fastest at every intersection. As you can imagine, this strategy might not lead to the fastest arrival time, since you might take some "easy" streets and then find yourself hopelessly stuck in a traffic jam.

2. Interview process are the greedy process.

***Knapsack problem***
objects : 1, 2, 3, 4, 5, 6, 7
profits: 10, 5, 3, 9, 2, 1, 4
weights: 2, 4, 3, 3, 2, 2, 1

Find the maximum object that can be selected in such a way that weight is equal to capacity of X where profite can be maximized.

Greedy solution - P/w choose maximum one.

2. Job sequencing problem

Jobs : 1, 2, 3, 4, 5, 6, 7
Profits: 30, 20, 19, 11, 10
deadlines: 2, 2, 1, 3, 3

sort the element with profits: in desc

maximu wait time - 3
0-1 - 2
1-2 - 1 
2-3 - 3

Maximum profit = 69

3. Optimal merge pattern problem

Lists - x1, x2, x3, x4, x5
sizes - 20, 30, 10, 5, 30

greedy use best methods -

merge minimum sizes two list ie - 
x3, x4 = 15, x5 = 30
x1, x2 = 50, + 30 = 80;

Huffman coding using greedy algorithm

send message over network in sort form

Minimum Cost spanning tree using greedy algorithm

- ****Kruskals and prims***

possible way of sapnning tree - E^C^(V-1) - no.of cycles

weighted graph then find minimum spanning tree

***Prims greedy algo**

steps1: select minimum edge
steps2: and then select minim cost edge between the different virtices edges.

*** kruskals approach ***

steps1: always select minimum edges between the vertices.
steps2: if any cycle is formed then select another edge.

performance of kruskals
O(V*E)

Performance can be improved by using min heap data structure of the edges

O(nlogn)

prims can not able to find min spinning tree in the disconnected graph but kruskal's can find min 
spinning tree's can find.

***Dijikstra Algorithm (single source shortest path)***
It uses greedy approach for directed and non directed graph.

1. It works well in all positive weighted graph but get fails in when weights re negative.

*** Dynamic programming ***
It uses recursion and tabular model.

recursion is top to bottom approach wherease tabular is bottom to top approach

In recursion by using meomoisation we can save the performance. 

Total number of binary tree is possible with n nodes is

2nCn/(n+1)

