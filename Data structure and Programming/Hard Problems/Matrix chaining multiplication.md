using System;
					
public class Program
{
	public static void Main()
	{
		 int[] arr = new int[]{ 40, 20, 30, 10, 30 }; 
		 int n = arr.Length;
		 Console.Write("Minimum number of multiplications is "
                          + MatrixChainOrder(arr, 1, n - 1)); 
	}
	
	public static int MatrixChainOrder(int[] arr, int i, int j){
		if(i==j) return 0;
		int min = int.MaxValue;
		for(int k = i; k<j; k++){
			int count = MatrixChainOrder(arr, i, k) + MatrixChainOrder(arr, k+1, j) + arr[i-1]*arr[k]*arr[j];
	        if(count < min){
				min = count;
			}
		}
		return min;
	}
}
// Exponential method

using System;
					
public class Program
{
	public static void Main()
	{
		int []arr = new int[] {1, 2, 3, 4}; 
        int size = arr.Length; 
  
        Console.Write("Minimum number of " +  
                             "multiplications is "+ 
                        MatrixChainOrder(arr, size)); 
	}
	public static int MatrixChainOrder(int[] arr, int n){
		int [ , ]m = new int[n, n]; 
		int q = 0;
		 for (int i = 1; i < n; i++) 
            m[i, i] = 0; 
		 for(int L = 2; L<n; L++){
			 for(int i=1; i < n-L+1; i++){
				
                int j = i+L-1; 
                if(j == n) continue; 
                m[i, j] = int.MaxValue; 
                for (int k = i; k <= j-1; k++) 
                { 
                    // q = cost/scalar multiplications 
                    q = m[i, k] + m[k+1, j] +  arr[i-1]*arr[k]*arr[j]; 
                    if (q < m[i, j]) 
                        m[i, j] = q; 
                } 
			 }
		 }
		 return m[1, n-1]; 
	}
	
}