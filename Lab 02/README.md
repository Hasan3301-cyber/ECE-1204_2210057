# Experiment No:02
# Date of Submission : 22-09-2024
# Experiment Name :
How to Work with virtual function.
# Theory :
A virtual function is a member function in a base class that you expect to override in derived classes. When you use a pointer or reference to the base class to call a virtual function, C++ determines which function to call based on the type of the object pointed to, not the type of the pointer/reference.
## Problem No : 05
## Write a C++ program to implement a class called Date that has private member variables for day, month, and year. Include member functions to set and get these variables, as well as to validate if the date is valid

---

### Code :

```
#include<iostream>
using namespace std;
class Date {
int Day;
int Month;
int Year;
public:
    Date(int a,int b,int c){
    Day =a;Month =b;Year=c;
    }
    void get(){

    if ((Year % 4 == 0 && Year % 100 != 0) || (Year % 400 == 0)){

     int month[] = { 31, 29, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31 };
     if(Month>0 && Month<13 && (Day <=month[Month])) {
        cout <<"Date is Valid"<<endl<<"Date is:"<<Day<<"-"<<Month<<"-"<<Year;
     }
     else {cout <<" Date is Invalid";}
    }
    else {
        int month[] = { 31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31 };
     if(Month>0 && Month<13 && (Day <=month[Month])) {
        cout <<"Date is Valid"<<endl<<"Date is:"<<Day<<"-"<<Month<<"-"<<Year;
     }
     else {cout <<" Date is Invalid";}
    }


}
};

int main(){
Date a(22,9,2024);
a.get();

}



```

### Output:
![Output5](https://github.com/user-attachments/assets/26b12866-071d-4cf8-90f6-7de308c05e1e)

## Problem No : 07
## Write a program in C++ to display the pattern like right angle triangle with number.

Sample Output:

Input number of rows: 5

1

12

123

1234

12345

---

### Code :

```
#include <iostream>
using namespace std;

int main() {
    int i, j, n;
    cout << "Enter number of rows: ";
    cin >> n;
    for (i = 0; i < n; i++) {
        for (j = 0; j <= i; j++) {
            cout << j + 1;
        }
        cout << endl;
    }

    return 0;
}


```

### Output:
![Output7](https://github.com/user-attachments/assets/2123f549-dad9-427f-a652-2699760f4674)


## Discussion and Conclusion:
In this lab class, we worked with the C++ programming language and focused on several fundamental concepts of object-oriented programming. We learned how work with virtual and abstract class and learned about polymorphism





