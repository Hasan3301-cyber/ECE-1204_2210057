# Experiment No:04
# Date of Submission : 04-10-2024
# Experiment Name :
Finding the largest string in a array of string using OOP concept.
# Theory :
An array is a collection of items stored at contiguous memory locations. It is used to store multiple values of the same type in a single variable.Passing arrays to an object typically occurs through the class constructor or through member functions. This allows the class to operate on the array data without exposing it directly to the outside world.
## Problem No : 04
Write a C++ program to find the third largest string in a given array of strings.(Use OOP Concept)
## 
### Code :

```
#include <iostream>
#include <string>
using namespace std;
class String {
    string *arr;
    int size;

public:
    String(string a[], int s) : size(s) {
        arr = new string[size];
        for (int i = 0; i < size; ++i) arr[i] = a[i];
    }
    string select () {
        string l1 = "", l2 = "", l3 = "";
        for (int i = 0; i < size; ++i) {
            if (arr[i].length() > l1.length()) {
                l3 = l2; l2 = l1; l1 = arr[i];
            } else if (arr[i].length() > l2.length()) {
                l3 = l2; l2 = arr[i];
            } else if (arr[i].length() > l3.length()) {
                l3 = arr[i];
            }
        }
        return l3;
    }
};

int main() {
    string arr[] = {"dog", "cat", "elephant", "cow", "zebra", "monkey"};
    int size = sizeof(arr) / sizeof(arr[0]);
    String x(arr, size);
    cout << "The third largest string by length is: " << x.select() << endl;
    return 0;
}


```

### Output:
![image](https://github.com/user-attachments/assets/c9b8d565-5918-46fc-b30b-bea019714a10)


## Discussion and Conclusion:
On this lab class, we tried to link up with procedural programming language that we can also solve the problem related to procedural programming language using oop concept. And We learned how to pass an array to object.






