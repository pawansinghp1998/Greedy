Q.1(392).Given two strings s and t, check if s is a subsequence of t.A subsequence of a string is a new string that isformed from the original string by deleting 
some (can be none) of the characters without disturbing the relative positions of theremaining characters. (i.e., "ace" is a subsequence of "abcde" while "aec" is not).

Input: s = "abc", t = "ahbgdc"
Output: true

Input: s = "axc", t = "ahbgdc"
Output: false
 
 class Solution {
    public boolean isSubsequence(String s, String t) {
        int z=0;int p=0;char ch1='a';char ch2='z';int k=0;int k1=0;
        int len1=s.length();
        if(s.equals(""))                                     //if subsequence is empty return true
            return true;
        for(int i=0;i<len1 && p<t.length();i++)
        {                                                      //we store value of i in k1 so that we can check whther we have reached till end of subsequence or not
             ch1=s.charAt(i);k1=i;                            //extracting cgaracter from subsequence
           for(int j=p;j<t.length();j++)        
           {
                ch2=t.charAt(j);
               if(ch1==ch2)
               {
                   p=j+1;                                //from this index we will chck character in next iteration
                   break;
               }
               if(ch1!=ch2 && j==t.length()-1)
                   k=-1;                             //if end of inner loop is reached and some cahracter has not been matched
           }
        }
            if(ch1==ch2 && k==0 && k1==len1-1)
                return true;
            else
                return false;
    }
}
