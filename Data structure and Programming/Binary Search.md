```

using System;
					
public class Program
{
	public static void Main()
	{
		int[] arr = {1,2,3,4,5,6,7,8,9};
		Console.WriteLine(BinarySearch(arr, arr.Length, 10));
	}
	
	public static int BinarySearch(int[] arr, int length,  int target){
		int start = 0;
		int end  = (length -1);
		
		while(start <= end){
			int mid = (start + end)/2;
			Console.WriteLine(mid);
			if(arr[mid] == target)
				return arr[mid];
			else if(arr[mid] < target)
				start = mid + 1;
			else 
				end = mid -1;
		    }
			return -1;
	}
}

```

steps: 

1. iterate over array from 0 to n-1;
2. if