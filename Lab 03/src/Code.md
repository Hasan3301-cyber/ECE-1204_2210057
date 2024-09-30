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
