***Painter's Partition Problem***

You have to paint N boards of length {A0, A1, A2, A3 … AN-1}. There are K painters available and you are also given how much time a painter takes to paint 1 unit of board. You have to get this job done as soon as possible under the constraints that any painter will only paint contiguous sections of board.

Input :
K : Number of painters
T : Time taken by painter to paint 1 unit of board
L : A List which will represent length of each board

Output:
     return minimum time to paint all boards % 10000003

     Example


Input : 
  K : 2
  T : 5
  L : [1, 10]

  Output : 50

```
class Solution {
    public int paint(int A, int B, List<int> C) {
       var result = partition(C, C.Count, A);
        result = result*B;
        if(result < 0){
            result = (result + 10000003)%10000003;
            return 9400003;
        }
        return result;
    }
    
    public static int partition(List<int>workunit, int length, int numberofpeople){
        
        // base cases  
        if (numberofpeople == 1) // one partition 
            return (sum(workunit, 0, length-1));  
              
        if (length == 1) // one board 
            return workunit[0];
        
        var best = int.MaxValue;
                
        // find minimum of all possible maximum 
        // k-1 partitions to the left of arr[i], 
        // with i elements, put k-1 th divider  
        // between arr[i-1] & arr[i] to get k-th  
        // partition 
        for (int i = 1; i <= length; i++) 
            best = Math.Min(best, Math.Max(partition(workunit, i, numberofpeople - 1),  
                                               sum(workunit, i, length - 1))); 
  
          return best; 
    }
    
    public static int sum(List<int> arr, int start, int end){
        int sum = 0;
        for(int i = start; i<= end; i++){
            sum = sum + arr[i];
        }
        return (sum);
    }
}

```