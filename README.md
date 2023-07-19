# Longest_Palindrome_subsequence_Solution
Longest Palindrome subsequence Solution

#include<bits/stdc++.h>

using namespace std;

class Solution{

  public:
   
     int longestPalinSubseq(string S) {
     
        //code here
        
         int dp[S.length()][S.length()];

        
        
        for (int i = S.length() - 1; i >= 0; i--) {
        
            dp[i][i] = 1;
            
            for (int j = i+1; j < S.length(); j++) {
            
                if (S[i] == S[j]) {
                
                    dp[i][j] = dp[i+1][j-1] + 2;
                
                } else {
                
                    dp[i][j] = max(dp[i+1][j], dp[i][j-1]);
                
                }
            
            }
        
        }
        
        return dp[0][S.length()-1];
    
    }

};


int32_t main()

{

    int t; cin >> t;
   
    while (t--)
    
    {
    
        string s; cin >> s;
        
        Solution ob;
        
        cout << ob.longestPalinSubseq(s) << endl;
    
    }
    
}
