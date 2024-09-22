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
