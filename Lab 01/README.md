# Experiment No:01
# Date of Submission : 22-09-2024
# Experiment Name :
Basic of C++ Language like how to Define Class and Object.
# Theory :
A class is a blueprint or template for creating objects. It defines the data (attributes or properties) and functions (methods or behaviors) that the objects created from the class will have.An object is an instance of a class.The objective is to design a C++ class and object.
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
#include <iostream>
using namespace std;
class Student {
    public:
        string name;
        int roll;
        string department;
        int series;
        int age;
    void display() {
        cout << "Student Information:" << endl;
        cout << "Name: " << name << endl;
        cout << "Roll Number: " << roll << endl;
        cout << "Department: " << department << endl;
        cout << "Series: " << series << endl;
        cout << "Age: " << age << endl;
    }
};

int main() {
    Student s1;
    cout << "Enter Student Name: ";
    getline(cin, s1.name);

    cout << "Enter Roll Number: ";
    cin >> s1.roll;

    cout << "Enter Department: ";
    cin >> s1.department;

    cout << "Enter Series: ";
    cin >> s1.series;

    cout << "Enter Age: ";
    cin >> s1.age;

    s1.display();

    return 0;
}


```

### Output :

![Output 2 (2)](https://github.com/user-attachments/assets/007bd056-65ff-4545-b7ca-d402bb5ef38b)



## Discussion and Conclusion:
In this lab class, we worked with the C++ programming language and focused on several fundamental concepts of object-oriented programming. We learned how to create classes and objects, how to initialize objects, and how to implement access modifiers like public and private




