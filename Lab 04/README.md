# Experiment No:04
# Date of Submission : 30-09-2024
# Experiment Name :
Finding the Student with Highest, Lowest Marks and Calculating the Average
# Theory :
A getter (or accessor) function is a method used in object-oriented programming to retrieve or "get" the value of a private attribute. It allows controlled access to an object's internal data without exposing the internal representation directly.A setter (or mutator) function is a method used to modify or "set" the value of a private attribute. It ensures that the attribute is modified in a controlled way, often allowing validation or additional processing before making changes.Using getter and setter function ,solved the problem
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
![LAB 03 OUTPUT 2](https://github.com/user-attachments/assets/aefc6d30-5188-49eb-9ee0-e90e501591cf)

## Discussion and Conclusion:
In this lab class, we worked with the C++ programming language and focused on several fundamental concepts of object-oriented programming. We learned how to use getter and setter function for the access of private data.







