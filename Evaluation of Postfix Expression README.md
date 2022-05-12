# DSA-Sheet-by-Arsh

// { Driver Code Starts
// C++ program to evaluate value of a postfix expression

#include <bits/stdc++.h>
using namespace std;


 // } Driver Code Ends
class Solution
{
    public:
    //Function to evaluate a postfix expression.
    int evaluatePostfix(string S)
    {
        stack<int> st;
        int a = 0, b = 0;
        
        for(int i = 0; i < S.length(); i++){
            if(isdigit(S[i]))
                st.push(S[i] - '0');
                
                switch(S[i]){
                    
                    case '+':
                        a = st.top(); st.pop();
                        b = st.top(); st.pop();
                        st.push(b+a);
                        break;
                        
                    case '-':
                        a = st.top(); st.pop();
                        b = st.top(); st.pop();
                        st.push(b-a);
                        break;
                        
                    case '*':
                        a = st.top(); st.pop();
                        b = st.top(); st.pop();
                        st.push(b*a);
                        break;
                        
                    case '/':
                        a = st.top(); st.pop();
                        b = st.top(); st.pop();
                        st.push(b/a);
                        break;
                }
        }
        return st.top();
    }
};

// { Driver Code Starts.

// Driver program to test above functions
int main()
{
    int t;
    cin>>t;
    cin.ignore(INT_MAX, '\n');
    while(t--)
    {
        string S;
        cin>>S;
        Solution obj;
    
    cout<<obj.evaluatePostfix(S)<<endl;
    }
    return 0;
}
  // } Driver Code Ends
