# Experiment No:03
# Date of Submission : 30-09-2024
# Experiment Name :
Finding the Student with Highest, Lowest Marks and Calculating the Average
# Theory :
A getter (or accessor) function is a method used in object-oriented programming to retrieve or "get" the value of a private attribute. It allows controlled access to an object's internal data without exposing the internal representation directly.A setter (or mutator) function is a method used to modify or "set" the value of a private attribute. It ensures that the attribute is modified in a controlled way, often allowing validation or additional processing before making changes.Using getter and setter function ,solved the problem
## Problem No : 02
## Write a c++ program to implement a class called student where the data field name ,id,mark. Show the name with highest mark student and lowest mark student and then show the average mark 

### Code :

```
#include <iostream>
#include <string>
using namespace std;

class Student {
private:
    int Id;
    int mark;
    string name;

public:
    void set(int a, int b, string c) {
        Id = a;
        mark = b;
        name = c;
    }
    int getId() {
        return Id;
    }

    int getMark() {
        return mark;
    }

    string getName() {
        return name;
    }
};

int main() {
    Student s1, s2, s3;
    Student high, low;
    s1.set(22, 18, "Mahim");
    s2.set(22, 15, "Rahim");
    s3.set(22, 19, "Jamal");
    high = s1;
    low = s1;
    if (s2.getMark() > high.getMark()) { high = s2; }
    if (s3.getMark() > high.getMark()) { high = s3; }
    if (s2.getMark() < low.getMark()) { low = s2; }
    if (s3.getMark() < low.getMark()) { low = s3; }
    cout << "Student with highest mark: " << high.getName() << " (" << high.getMark() << ")" << endl;
    cout << "Student with lowest mark: " << low.getName() << " (" << low.getMark() << ")" << endl;
    double avg = (s1.getMark() + s2.getMark() + s3.getMark()) / 3.0;
    cout << "Average = " << avg << endl;

    return 0;
}



```

### Output:
![LAB 03 OUTPUT 2](https://github.com/user-attachments/assets/aefc6d30-5188-49eb-9ee0-e90e501591cf)

## Discussion and Conclusion:
In this lab class, we worked with the C++ programming language and focused on several fundamental concepts of object-oriented programming. We learned how to use getter and setter function for the access of private data.






