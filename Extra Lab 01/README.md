# Experiment No:05
# Date of Submission : 17-10-2024
# Experiment Name :
Using OOP concept(Operator Overloading,Inheritance,Polymorphism) solve different kinds of problem.
# Theory :
Operator Overloading,it allows you to redefine how operators (like +, ==, >) work with objects of a class, enabling them to perform specific actions based on the class’s behavior. Example: Using + to add two objects of a custom class.Inheritance,it is a mechanism where a new class (subclass) inherits properties and methods from an existing class (superclass), promoting code reuse and hierarchy. Example: A Manager class inherits from an Employee class.Polymorphism,it allows objects of different classes to be treated as objects of a common superclass, enabling the use of a single interface for different underlying forms (e.g., method overriding). Example: Different shapes (like Circle, Rectangle) implementing the same area() method.
## Problem No : 01
Create a class called Book with attributes such as title, author, and price. Include a method
to display the book's details. Write a program that instantiates a Book object and displays
its details.


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
        cout << "Price: " << price << endl;
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

![image](https://github.com/user-attachments/assets/7c8362f2-970b-438a-8769-9398ac9dd582)


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
#include <iostream>
#include <vector>
#include <string>
using namespace std;
class Book {
private:
    string title;
    string author;
    double price;

public:
    Book(string t, string a, double p)   {
    title=t;
    author=a;
    price=p;
    }
    void display()  {
        cout << "Title: " << title << ", Author: " << author << ", Price: " << price << endl;
    }
    string get()  {
        return title;
    }
};
class Library {
private:
    vector<Book> books;

public:
    void add(Book &book) {
        books.push_back(book);
        cout << "Book added: " << book.get() << endl;
    }
    void rem( const string &title) {
        for (int i = 0; i < books.size(); i++) {
            if (books[i].get() == title) {
                books.erase(books.begin() + i);
                cout << "Book removed: " << title << endl;
                return;
            }
        }
        cout << "Book not found: " << title << endl;
    }
    void display2() {

            cout << "Available books in the library now:" << endl;
            for(int i=0;i<books.size();i++){

            books[i].display();
        }

}
};

int main() {
    Library library;

    Book book1("Math", "hk das", 568);
    Book book2("Chemistry", "hajari", 786);
    Book book3("Physics", "amir", 340);
    library.add(book1);
    library.add(book2);
    library.add(book3);
    cout << endl;
    library.display2();
    cout << endl;
    library.rem("Chemistry");
    cout << endl;
    library.display2();

    return 0;
}



```

### Output:
![image](https://github.com/user-attachments/assets/f2a203d7-1c77-4844-827f-989e4d2dea99)


## Problem No : 07
Create a class ShoppingCart that holds a list of Product objects. Implement methods
to add items to the cart, remove items, and calculate the total price. Write a program to test
the functionality of the ShoppingCart class.

### Code :

```
#include <iostream>
#include <vector>
#include <string>
using namespace std;
class Product {
private:
    string name;
    double price;

public:
    Product(string n, double p) {
        name = n;
        price = p;
    }

    double getPrice() const {
        return price;
    }

    string getName() const {
        return name;
    }

    void display() const {
        cout << "Product: " << name << ", Price: " << price << endl;
    }
};

class ShoppingCart {
private:
    vector<Product> cart;

public:
    void add(const Product &p) {
        cart.push_back(p);
        cout << "Added to cart: " << p.getName() << endl;
    }

    void remov(const string &name) {
        for (int i = 0; i < cart.size(); ++i) {
            if (cart[i].getName() == name) {
                cout << "Removed from cart: " << cart[i].getName() << endl;
                cart.erase(cart.begin() + i);
                return;
            }
        }
        cout << "Product not found: " << name << endl;
    }

    double total()  {
        double total = 0.0;
        for (int i = 0; i < cart.size(); ++i) {
            total =total+ cart[i].getPrice();
        }
        return total;
    }

    void display2()  {

            for (int i = 0; i < cart.size(); ++i) {
                cart[i].display();
            }
            cout << "Total Price: " << total() << endl;
        }

};

int main() {
    ShoppingCart cart;

    Product p1("Laptop", 999.99);
    Product p2("Smartphone", 699.99);
    Product p3("Headphones", 49.99);

    cart.add(p1);
    cart.add(p2);
    cart.add(p3);

    cout << endl;
    cart.display2();

    cout << endl;
    cart.remov("Smartphone");

    cout << endl;
    cart.display2();

    cout << endl;
    cart.remov("Tablet");

    return 0;
}

```

### Output:
![image](https://github.com/user-attachments/assets/b5397bfe-130a-40d1-97a1-04156b9abfae)


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
#include <vector>
#include <string>
using namespace std;

class Student {
private:
    int id;
    string name;

public:
    Student(int i, string n) {
        id = i;
        name = n;
    }

    int getId() {
        return id;
    }

    string getName() {
        return name;
    }

    void display() {
        cout << "ID: " << id << ", Name: " << name << endl;
    }
};

class School {
private:
    vector<Student> students;

public:
    void add( Student &o) {
        students.push_back(o);
        cout << "Student added: " << o.getName() << endl;
    }

    void remov(int id) {
        for (int i = 0; i < students.size(); ++i) {
            if (students[i].getId() == id) {
                cout << "Student removed: " << students[i].getName() << endl;
                students.erase(students.begin() + i);
                return;
            }
        }
        cout << "Student with ID " << id << " not found." << endl;
    }

    void searcha(int id) {
        for (int i = 0; i < students.size(); ++i) {
            if (students[i].getId() == id) {
                cout << "Student found: ";
                students[i].display();
                return;
            }
        }
        cout << "Student with ID " << id << " not found." << endl;
    }

    void display2() {
        for (int i = 0; i < students.size(); ++i) {
            students[i].display();
        }
    }
};

int main() {
    School s;
    Student s1(40, "rahim");
    Student s2(90, "jamal");
    Student s3(17, "hasan");

    s.add(s1);
    s.add(s2);
    s.add(s3);

    cout << endl;
    s.display2();

    cout << endl;
    s.searcha(40);

    cout << endl;
    s.remov(40);

    cout << endl;
    s.display2();

    return 0;
}

```

### Output:

![image](https://github.com/user-attachments/assets/11ea64c1-d24f-42b6-8367-969b1f063516)


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

![image](https://github.com/user-attachments/assets/d728058a-8b14-4752-a1b3-0a69634659cc)

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
Define a class Complex with private members real and imaginary. Overload the
operators +, -, *, and / to perform addition, subtraction, multiplication, and division of
two complex numbers, respectively. Create a constructor to initialize the complex number
and include a method to display the result. The main() function should be used to test
these overloaded operators.

### Code :

```
#include <iostream>
using namespace std;

class Complex {
private:
    double r;
    double m;

public:
    Complex(double a , double b) {
        r = a;
        m = b;
    }
    void display() const {
        if (m >= 0)
            cout << r << " + " << m << "i" << endl;
        else
            cout << r << " - " << -m << "i" << endl;
    }
    Complex operator+(const Complex &o)  {
        return Complex(r + o.r, m + o.m);
    }

    Complex operator-(const Complex &o)  {
        return Complex(r - o.r, m - o.m);
    }
    Complex operator*(const Complex &o)  {
        double x = (r * o.r) - (m * o.m);
        double y = (r * o.m) + (m * o.r);
        return Complex(x, y);
    }
    Complex operator/(const Complex &o)  {
        double d = o.r * o.r + o.m * o.m;
        double x = (r * o.r + m * o.m) / d;
        double y = (m * o.r - r * o.m) / d;
        return Complex(x, y);
    }
};

int main() {
    Complex c1(4.0, 5.0);
    Complex c2(2.0, 3.0);
    cout << "Complex number 1: ";
    c1.display();
    cout << "Complex number 2: ";
    c2.display();
    Complex r = c1 + c2;
    cout << "\nAddition: ";
    r.display();
    r = c1 - c2;
    cout << "Subtraction: ";
    r.display();
    r = c1 * c2;
    cout << "Multiplication: ";
    r.display();
    r = c1 / c2;
    cout << "Division: ";
    r.display();

    return 0;
}



```

### Output:

![image](https://github.com/user-attachments/assets/5e3c4e06-eee8-4c20-b90f-8b5dd04d443e)


## Problem No : 13
Define a class Rectangle with private members length and breadth. Overload the
operators == to check if two rectangles have equal areas, and > and < to compare if one
rectangle is larger or smaller than the other based on area. Implement a constructor to
initialize the rectangle's dimensions and a method to calculate its area. The main()
function should test the overloaded operators.
### Code :

```
#include <iostream>
using namespace std;
class Rect {
private:
    double len;
    double breadth;

public:
    Rect(double l , double b) {
        len = l;
        breadth = b;
    }
    double area() const {
        return len * breadth;
    }
    bool  operator==(const Rect &other)  {
        return this->area() == other.area();
    }
    bool operator>(const Rect &other)  {
        return this->area() > other.area();
    }
    bool operator<(const Rect &other)  {
        return this->area() < other.area();
    }
    void display() const {
        cout << "Length: " << len << ", Breadth: " << breadth << ", Area: " << area() << endl;
    }
};
int main() {
    Rect rect1(5.0, 4.0);
    Rect rect2(6.0, 3.0);
    cout << "Rectangle 1: ";
    rect1.display();
    cout << "Rectangle 2: ";
    rect2.display();
    if (rect1 == rect2) {
        cout << "The two rectangles have equal areas." << endl;
    } else {
        cout << "The two rectangles do not have equal areas." << endl;
    }
    if (rect1 > rect2) {
        cout << "Rectangle 1 is larger than Rectangle 2." << endl;
    } else {
        cout << "Rectangle 1 is not larger than Rectangle 2." << endl;
    }
    if (rect1 < rect2) {
        cout << "Rectangle 1 is smaller than Rectangle 2." << endl;
    } else {
        cout << "Rectangle 1 is not smaller than Rectangle 2." << endl;
    }

    return 0;
}


```

### Output:
![image](https://github.com/user-attachments/assets/96813693-ed10-4684-9a9a-7d7afbc4ffc5)

## Discussion:
On those lab problem we use oop concept to solve 
