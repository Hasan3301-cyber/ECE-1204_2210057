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
