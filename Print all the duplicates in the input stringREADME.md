# DSA-Sheet-by-Arsh

#include <iostream>
#include <string>
#include <unordered_map>
using namespace std;

void printDuplicate(string str)
{
    unordered_map<char, int> count;
    for (int i = 0; i < str.length(); i++)
    {
        count[str[i]]++;
    }

    for (auto it : count)
    {
        if (it.second > 1)
            cout << it.first << ", count = " << it.second << "\n";
    }
}

int main()
{
    string str;
    cout << "Enter a string -  ";
    cin >> str;

    printDuplicate(str);
}
