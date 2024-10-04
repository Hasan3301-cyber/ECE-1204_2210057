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
