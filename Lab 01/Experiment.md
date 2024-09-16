## Problem No : 01
## Write a program to store and display multiple cars, including model, color , mileage and brand into details.

---

### Code :

```
#include <iostream>
#include <string>
using namespace std;
class Car {
public:
    double mi;
    string co;
    string mod;
    string b;
    void display() {
        cout << "Mileage: " << mi << endl;
        cout << "Color: " << co << endl;
        cout << "Model: " << mod << endl;
        cout << "Brand: " << b << endl;
        cout << endl;
    }
};
int main() {
    Car s[2];
    for (int i = 0; i < 2; ++i) {
        cout << "Enter mileage for Car " << (i + 1) << ": ";
        cin >> s[i].mi;
        cin.ignore();
        cout << "Enter color for Car " << (i + 1) << ": ";
        getline(cin, s[i].co);
        cout << "Enter model for Car " << (i + 1) << ": ";
        getline(cin, s[i].mod);
        cout << "Enter brand for Car " << (i + 1) << ": ";
        getline(cin, s[i].b);
        cout<<endl;
    }
    for (int i = 0; i < 2; ++i) {
        cout << "Information for Car " << (i + 1) << ":" << endl;
        s[i].display();
        cout<<endl;
    }
    return 0;
}

```

### Output:

![image](https://github.com/user-attachments/assets/bfc0bfaf-adcb-4a62-9e30-2342a2e4ef6c)


## Problem No : 02
## Write a program to store and display the student info of a universersity student including name, roll, department, series, age.

### Code:

```


```

### Output :

![image](https://github.com/user-attachments/assets/604b5eca-ab62-4df8-9fcf-94d01b07c2d2)



## Discussion :



