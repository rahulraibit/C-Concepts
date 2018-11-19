***Find Sqrt of the given number***

```
int Solution::sqrt(int A) {
    // Do not write main() function.
    // Do not read input, instead use the arguments to the function.
    // Do not print the output, instead return values as specified
    // Still have a doubt. Checkout www.interviewbit.com/pages/sample_codes/ for more details
    if (A == 0 || A == 1)  
       return A; 
  
    // Do Binary Search for floor(sqrt(x)) 
    int start = 1, end = A, ans = 0;    
    while (start <= end)  
    {         
        long mid = (long)((long)start + (long)end) / 2; 
  
        // If x is a perfect square 
        if ((long)mid*mid == (long)A) 
            return (int)mid; 
  
        // Since we need floor, we update answer when mid*mid is  
        // smaller than x, and move closer to sqrt(x) 
        if ((long)mid*mid < (long)A)  
        { 
            start = (int)mid + 1; 
            ans = (int)mid; 
        }  
        else // If mid*mid is greater than x 
            end = (int)mid-1;         
    } 
    return ans; 
    
}
```