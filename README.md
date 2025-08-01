# valid-anagram
A C++ program that checks whether two given strings are valid anagrams by using character frequency comparison.

#include <iostream>
#include <unordered_map>
using namespace std;

bool isAnagram(string s, string t) {
    if (s.length() != t.length()) return false;

    unordered_map<char, int> freq;

    for (char c : s) freq[c]++;
    for (char c : t) {
        freq[c]--;
        if (freq[c] < 0) return false;
    }

    return true;
}

int main() {
    string str1, str2;
    cout << "Enter first string: ";
    cin >> str1;
    cout << "Enter second string: ";
    cin >> str2;

    if (isAnagram(str1, str2))
        cout << "Yes, they are valid anagrams." << endl;
    else
        cout << "No, they are not anagrams." << endl;

    return 0;
}

