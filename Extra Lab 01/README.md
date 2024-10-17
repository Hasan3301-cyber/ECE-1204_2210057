# Experiment No:05
# Date of Submission : 17-10-2024
# Experiment Name :
Basic of C++ Language like how to Define Class and Object.
# Theory :
A class is a blueprint or template for creating objects. It defines the data (attributes or properties) and functions (methods or behaviors) that the objects created from the class will have.An object is an instance of a class.The objective is to design a C++ class and object.
## Problem No : 01
Create a class called Book with attributes such as title, author, and price. Include a method
to display the book's details. Write a program that instantiates a Book object and displays
its details.

---

### Code :

```
#include <iostream>
#include <string>
using namespace std;
class Book {
private:
    string title;
    string author;
    double price;

public:
    Book(string a, string b, double c) {
        title = a;
        author = b;
        price = c;
    }

    void display() {
        cout << "Title: " << title << endl;
        cout << "Author: " << author << endl;
        cout << "Price: $" << price << endl;
    }
};
int main() {
    Book x("Math", "hk das", 1000);

    cout << "Book Details:" << endl;
    x.display();

    return 0;
}



```

### Output:

![image](https://github.com/user-attachments/assets/8441f996-e9a7-4f61-9e1d-ff6fc3d8c2fe)


## Problem No : 02
Develop a class Student that has attributes for student ID and name. Include a method
to display the student's information. Create an instance of the Student class and print its
details.

### Code :

```
#include <iostream>
#include <string>
using namespace std;
class Student {
private:
    int ID;
    string name;

public:
    Student(int a, string b) {
        ID = a;
        name = b;
    }

    void display() {
        cout << "Student ID: " << ID << endl;
        cout << "Name: " << name << endl;
    }
};
int main() {
    Student s(2210057, "Hasan");
    cout << "Student Information:" << endl;
    s.display();

    return 0;
}


```

### Output:

![image](https://github.com/user-attachments/assets/bb5c27db-8dff-42b6-96f3-11a8356ae2b1)


## Problem No : 03
Implement a class called Calculator with methods for basic arithmetic operations
(addition, subtraction, multiplication, division). Write a program that allows the user to
perform calculations using the Calculator class.

### Code :

```
#include <iostream>
using namespace std;
class Calculator {
public:
    double add(double a, double b) {
        return a + b;
    }
    double subtract(double a, double b) {
        return a - b;
    }
    double multiply(double a, double b) {
        return a * b;
    }
    double divide(double a, double b) {
        if (b == 0) {
            cout << "Error: Division by zero is undefined!" << endl;
            return 0;
        }
        return a / b;
    }
};
int main() {
    Calculator cal;
    double a, b, result;
    char op;
    cout << "Enter the first number: ";
    cin >> a;

    cout << "Enter an operator : ";
    cin >> op;

    cout << "Enter the second number: ";
    cin >> b;
    switch (op) {
        case '+':
            result = cal.add(a, b);
            cout << "Result: " << result << endl;
            break;
        case '-':
            result = cal.subtract(a, b);
            cout << "Result: " << result << endl;
            break;
        case '*':
            result = cal.multiply(a, b);
            cout << "Result: " << result << endl;
            break;
        case '/':
            result = cal.divide(a, b);
            cout << "Result: " << result << endl;
            break;
        default:
            cout << "Error: Invalid operator!" << endl;
    }

    return 0;
}


```

### Output:

![image](https://github.com/user-attachments/assets/f4691bd9-cc9a-4fb8-b340-d06442620a5f)

## Problem No : 04
Create a Person class with attributes for name and age. Implement a method to check if
the person is an adult (18 years or older). Instantiate a Person object and check if they
are an adult.

### Code :
```
#include <iostream>
#include <string>
using namespace std;
class Person {
private:
    string name;
    int age;

public:
    Person(string n, int a) {
        name = n;
        age = a;
    }
    int X() {
        if( age >= 18){return 1;}
        else {return 0;}
    }
    void display() {
        cout << "Name: " << name << endl;
        cout << "Age: " << age << endl;
        if (X()) {
            cout << name << " is an adult." << endl;
        } else {
            cout << name << " is not an adult." << endl;
        }
    }
};
int main() {
    Person a("Jamal", 20);
    a.display();

    return 0;
}

```
### Output:

![image](https://github.com/user-attachments/assets/4aac9e51-664c-4322-a6d4-56b15818f418)


## Problem No : 05
Design a class hierarchy with a base class Employee and subclasses Manager and
Intern. Implement methods to calculate and display the salary of each type of employee.
Write a program that demonstrates the use of inheritance and method overriding.
### Code :

```
#include <iostream>
#include <string>
using namespace std;
class Employee {
protected:
    string name;
    double Salary;

public:
    Employee(string a, double b) {
        name = a;
        Salary = b;
    }

    virtual double cal() {
        return Salary;
    }

    virtual void display() {
        cout << "Employee Name: " << name << endl;
        cout << "Salary: " << cal() << endl;
    }
};
class Manager : public Employee {
private:
    double bonus;

public:
    Manager(string a, double b, double c)
        : Employee(a, b) {
        bonus = c;
    }
    double cal() override {
        return Salary + bonus;
    }
    void display() override {
        cout << "Manager Name: " << name << endl;
        cout << "Base Salary: " << Salary << endl;
        cout << "Bonus: " << bonus << endl;
        cout << "Total Salary: " << cal() << endl;
    }
};
class Intern : public Employee {
private:
    int hour;
    double rate;

public:
    Intern(string a, int b, double c)
        : Employee(a, 0) {
        hour = b;
        rate = c;
    }
    double cal() override {
        return hour* rate;
    }
    void display() override {
        cout << "Intern Name: " << name << endl;
        cout << "Work Hours: " << hour << endl;
        cout << "Hourly Rate: " << rate << endl;
        cout << "Total Salary: " << cal() << endl;
    }
};
int main() {
    Manager a("Jamal", 50000, 15000);
    cout << "Manager Details:" << endl;
    a.display();
    cout << endl;
    Intern b("Kamal", 160, 150);
    cout << "Intern Details:" << endl;
    b.display();
    cout << endl;
    return 0;
}


```

### Output:

![image](https://github.com/user-attachments/assets/513699ce-6b62-47be-b965-fcb7cb95fdea)


## Problem No : 06
Implement a class called Library that manages a collection of Book objects. Include
methods to add and remove books, as well as display all available books. Write a program
to test the functionality of the Library class.

### Code :

```


```

### Output:

![image](https://github.com/user-attachments/assets/bfc0bfaf-adcb-4a62-9e30-2342a2e4ef6c)

## Problem No : 07
Create a class ShoppingCart that holds a list of Product objects. Implement methods
to add items to the cart, remove items, and calculate the total price. Write a program to test
the functionality of the ShoppingCart class.

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

## Problem No : 08
Write an abstract class called Appliance with an abstract method turnOn(). Create
subclasses WashingMachine and Refrigerator that implement this method. Write
a program that demonstrates method overriding(function overriding).

### Code :

```
#include <iostream>
using namespace std;
class Appliance {
public:
    virtual void turnOn() = 0;
};
class WashingMachine : public Appliance {
public:
    void turnOn() override {
        cout << "Washing machine is now ON" << endl;
    }
};
class Refrigerator : public Appliance {
public:
    void turnOn() override {
        cout << "Refrigerator is now ON" << endl;
    }
};
int main() {
    Appliance* p;
    WashingMachine a;
    p=&a;
    p->turnOn();
    Refrigerator b;
    p=&b;
    p->turnOn();

    return 0;
}

```

### Output:
![image](https://github.com/user-attachments/assets/793ccc57-786c-4266-8fef-993cdead5251)


## Problem No : 09
Design a class School that manages a collection of Student objects. Implement
methods to add, remove, and search for students by ID. Write a program to test the School
class.

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

## Problem No : 10
Create a class Game that has methods to start, pause, and end the game. Implement a
method to display the game's status. Write a program that simulates a simple game using
the Game class.

### Code :

```
#include <iostream>
#include <string>
using namespace std;
class Game {
private:
    string status;
public:
    Game() : status("Not started") {}
    void start() {
        status = "Running";
        cout << "Game started!" << endl;
    }
    void pause() {
        if (status == "Running") {
            status = "Paused";
            cout << "Game paused." << endl;
        } else {
            cout << "Can't pause. Game is not running." << endl;
        }
    }
    void end() {
        status = "Ended";
        cout << "Game ended." << endl;
    }
    void display()  {
        cout << "Current game status: " << status << endl;
    }
};
int main() {
    Game a;
    a.display();
    a.start();
    a.display();
    a.pause();
    a.display();
    a.pause();
    a.end();
    a.display();

    return 0;
}



```

### Output:

![image](https://github.com/user-attachments/assets/813fa463-33e2-44ef-87f6-46fa11194118)

## Problem No : 11
Design a class Person that includes a static variable to count the number of Person
objects created. Implement a method to display the total count of persons. Write a program
that creates several Person objects and displays the count.
### Code :

```
#include <iostream>
using namespace std;
class Person {
private:
    static int count;
    string name;

public:
    Person()  {
        count++;
    }
    static void display() {
        cout << "Total number of Person objects created: " << count << endl;
    }
};
int Person::count = 0;

int main() {
    Person a;
    Person b;
    Person c;
    Person::display();

    return 0;
}


```

### Output:

![image](https://github.com/user-attachments/assets/cf81b065-7caa-4553-af54-173935ae8653)


## Problem No : 12
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

## Problem No : 13
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

## Problem No : 14
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

## Problem No : 15
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

## Problem No : 16
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

## Problem No : 17
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




