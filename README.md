**Object-Oriented Programming**

---

### **Features of OOPS**
- **Abstraction**
- **Data Hiding**
- **Inheritance**
- **Polymorphism**

---

### **Classes**
- **Class is a blueprint of an object**
- **Class is a group of objects**
- **Class is a design of an object**
- Many objects can be created from the same class.
- An object consumes memory equal to the sum of sizes of all data members.
- Member functions don’t occupy memory.
- Member functions are called depending on the object.
- The **dot (.) operator** is used for accessing members of an object.
- Memory allocated for an object is often referred to as an **instance**.

---

### **Class Example 1**
```cpp
Class Rectangle
{
public:
    int length;
    int breadth;

    int area()
    {
        return length * breadth;
    }

    int perimeter()
    {
        return 2 * (length + breadth);
    }
};
```

---

### **Class Example 2**
**Write all functions for Rectangle**

```cpp
class Rectangle
{
private:
    int length;
    int breadth;

public:
    Rectangle();
    Rectangle(int l, int b);
    Rectangle(Rectangle &r);

    int getLength() { return length; }
    int getBreadth() { return breadth; }

    void setLength(int l);
    void setBreadth(int b);
    int area();
    int perimeter();
    bool isSquare();
    ~Rectangle();
};

int main()
{
    Rectangle r1(10, 10);
    cout << "Area " << r1.area() << endl;
    if (r1.isSquare())
        cout << "Yes" << endl;
}

Rectangle::Rectangle()
{
    length = 1;
    breadth = 1;
}

Rectangle::Rectangle(int l, int b)
{
    length = l;
    breadth = b;
}

Rectangle::Rectangle(Rectangle &r)
{
    length = r.length;
    breadth = r.breadth;
}

void Rectangle::setLength(int l)
{
    length = l;
}

void Rectangle::setBreadth(int b)
{
    breadth = b;
}

int Rectangle::area()
{
    return length * breadth;
}

int Rectangle::perimeter()
{
    return 2 * (length + breadth);
}

bool Rectangle::isSquare()
{
    return length == breadth;
}

Rectangle::~Rectangle()
{
    cout << "Rectangle Destroyed";
}
```

---

### **Pointer to an Object**
- A pointer of type class can be created.
- A pointer can point to an existing object.
- A new object can be created in the heap using a pointer.
- The **arrow operator** is used for accessing members of an object using a pointer.

---

### **Data Hiding**
- Data members of a class are usually declared as **Private** or **Protected**.
- They can be accessed only inside the class and its child classes.
- Data hiding protects data from mishandling.

---

### **Constructors**
- A constructor is a member function of a class.
- It will have the **same name as the class name**.
- It does **not have a return type**.
- It is usually declared as **public**, but can also be private in some cases.
- It is called when an object is created.
- It is used for initializing an object.
- It can be overloaded.
- If not defined, the class will have a default constructor.
- A constructor can take default arguments.

#### **Types of Constructors**
1. Non-argument constructor
2. Parameterized constructor
3. Copy constructor

---

### **All Types of Member Functions**
1. **Constructors**: Called when an object is created.
2. **Accessors**: Used for retrieving the value of data members.
3. **Mutators**: Used for modifying the value of data members.
4. **Facilitators**: Represent the actual functionality of the class.
5. **Enquiry Functions**: Used for checking if an object satisfies certain conditions.
6. **Destructor**: Used for releasing resources allocated by the object.

---

### **Program with a Class for Student**
```cpp
#include<iostream>
using namespace std;

class Student
{
private:
    int roll;
    string name;
    int mathMarks;
    int phyMarks;
    int chemMarks;

public:
    Student(int r, string n, int m, int p, int c)
    {
        roll = r;
        name = n;
        mathMarks = m;
        phyMarks = p;
        chemMarks = c;
    }

    int total()
    {
        return mathMarks + phyMarks + chemMarks;
    }

    char grade()
    {
        float average = total() / 3;
        if (average > 60)
            return 'A';
        else if (average >= 40 && average < 60)
            return 'B';
        else
            return 'C';
    }
};

int main()
{
    int roll;
    string name;
    int m, p, c;

    cout << "Enter Roll number of a Student: ";
    cin >> roll;
    cout << "Enter Name of a Student: ";
    cin >> name;
    cout << "Enter marks in 3 subjects: ";
    cin >> m >> p >> c;

    Student s(roll, name, m, p, c);

    cout << "Total Marks: " << s.total() << endl;
    cout << "Grade of Student: " << s.grade() << endl;

    return 0;
}
```


---
### ***Operator overloading*** 
1. • Operators can be overloaded on our classes
2. • We can define operator for our own classes
3. • Operators can be overloaded using member functions or friend functions
4. • Global functions can also access private and protected members of an object if they are 
declared as friend inside a class
```cpp
class Complex
{
private:
 int real;
 int img;
public:
 Complex(int r=0,int i=0)
 {
 real=r;
 img=i;
 } 
 void display() 
 { 
 cout<<real<<“+i”<<img<<endl; 
 } 
 Complex operator+(Complex c)
 { 
 Complex temp;
 temp.real=real+c1.real; 
 temp.img=img+c1.img;
 return temp;
 }
 };
int main()
{
 Complex c1(5,3),c2(10,5),c3;
 
 c3=c1+c2;
 
 c3.display();
}
```











