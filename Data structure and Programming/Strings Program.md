Given a string, determine if it is a palindrome, considering only alphanumeric characters and ignoring cases.

Example:

"A man, a plan, a canal: Panama" is a palindrome.

"race a car" is not a palindrome.

Return 0 / 1 ( 0 for false, 1 for true ) for this problem


class Solution {
    public int isPalindrome(string A) {
        var str = A;
        int l = 0; 
        int h = str.Length - 1; 
          
        // Lowercase string 
        str = str.ToLower(); 
          
        // Compares character until  
        // they are equal 
        while(l <= h) 
        { 
              
            char getAtl = str[l]; 
            char getAth = str[h]; 
              
            // If there is another symbol  
            // in left of sentence 
            if (!(getAtl >= 'a' &&  
                  getAtl <= 'z') && !char.IsNumber(getAtl)) 
                l++; 
              
            // If there is another symbol   
            // in right of sentence 
            else if(!(getAth >= 'a' && 
                       getAth <= 'z') && !char.IsNumber(getAth)) 
                h--; 
              
            // If characters are equal 
            else if( getAtl == getAth) 
            { 
                l++; 
                h--; 
            } 
              
            // If characters are not equal then 
            // sentence is not palindrome 
            else
                return 0; 
        } 
          
        // Returns true if sentence  
        // is palindrome 
        return 1; 
    }
}
