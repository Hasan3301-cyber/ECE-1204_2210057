## Code -1:

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
## Code -2:
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
## Code -3:
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
## Code -4:
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
## Code -5:
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
## Code -6:

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
## Code -7:
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
## Code -8:
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
## Code -9:
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
## Code -10:
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
## Code -11:
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
## Code -12:
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
## Code -13:
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
