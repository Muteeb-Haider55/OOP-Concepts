
---

## **Pointers**

### 1. Data Variables vs Address Variables**
```cpp
int x = 10;  // Data variable
int *p;      // Address variable (declaration)
p = &x;      // Initialization
cout << *p;  // Dereferencing -> Output: 10
```
### . Data Variables vs Address Variables**
A program can access code section and stack directly.
However, it cannot access the heap directly.
Pointers allow indirect access to heap memory.

```cpp
int A[5] = {1, 2, 3, 4, 5}; // Array in stack section
int *p;
p = new int[5];  // Allocates memory in the heap using `new`
delete[] p;      // Deallocates heap memory to prevent memory leaks
```
### **2. Pointer Arithmetic
```cpp
int A[5] = {2, 4, 6, 8, 10};
int *P = A;  // Pointer points to the first element of array
```
### **3. Operations
P++ - Move to the next memory location
(Pointer moves bytes based on its data type. E.g., for int, if initial address = 200, next address = 204)
P-- - Move to the previous location
P = P + 2 - Jump two positions ahead
P = P - 2 - Jump two positions back
d = P - Q - Difference between two pointers
### **4. Common Pointer Problems
> Uninitialized Pointer
```cpp
int *p;
*p = 25;  // Undefined behavior
```
Memory Leak
```cpp
int *p = new int[5];
// Forgetting `delete[] p` causes memory to remain allocated
```
# Dangling Pointer
```cpp
int *p = new int[5];
delete[] p;
p = NULL;  // Accessing memory after deallocation
```
# References
```cpp
int x = 10;
int &y = x;  // Reference variable must be initialized at declaration
x++;
y++;

cout << x;  // Output: 11
cout << y;  // Output: 11
```
# Key Points
- No extra memory is consumed by references (same memory as the variable).
- Once initialized, cannot reassign the reference to another variable.
- Both variable and reference share the same address:
```cpp
cout << &x << " " << &y;  // Output: same address
```
# Pointers to Functions
Example: Pointing to and Calling Functions
```cpp
void display() {
    cout << "HELLO";
}
int main() {
    void (*fp)();
    fp = display;  // Assign pointer to function
    (*fp)();       // Call function via pointer
}
```
- Example: Multiple Functions with Same Signature
```cpp
int max(int x, int y) {
    return x > y ? x : y;
}
int min(int x, int y) {
    return x < y ? x : y;
}
int main() {
    int (*fp)(int, int);
    
    fp = max;       // Assign `max` function to pointer
    (*fp)(10, 5);   // Call `max` function
    
    fp = min;       // Assign `min` function to pointer
    (*fp)(10, 5);   // Call `min` function
}
```
Function pointers are useful in runtime polymorphism.

 # Introduction to OOP
- Modular Programming
- Object Oriented Programming
#  Example: Bank Operations M.P
```cpp
open_account();
deposit_account();
withdraw();
check_bal();
apply_loan();
```
Object-Oriented Programming
Example: Govt Department Operations
---
```cpp
Electric
pay_bill();
Water
...
Education
...
Transport
TicketBook();
selectSeat();
Bank
open_account();
deposit_account();
withdraw();
check_bal();
apply_loan();

```
# Writing a Class
Class is the blue print of object
class occupy no space in stack
```cpp
class Rectangle{
public: //By default all data members of class are private
int length;
int breadth; 

int area(){
return length*breadth;
}
int  perimeter(){
return 2*(length + breadth);
}
};

// Main function
int main(){
Rectangle r1,r2;//we can create n numbers of objects
//r1 and r2 are objects and each objects occupied some memory in  stack
//  if integer takes two bytes then r1 occupied 4 bytes and r2 also

//Use Dot Operater to access the public members of class
r1.length=10;
r1.breadth=5;
cout<<r1.area();
r2.length=20;
r2.breadth=5;
cout<<r2.area();
}

```
Pointer to an Object
```cpp
// I use Rectangle class here
int main(){
Rectangle r1;
Rectangle *ptr; // We also Create a dynamic object   Rectangle *ptr=new Rectangle
ptr=&r;
ptr->length=10;
ptr->breadth=10;
cout<<ptr->area()<<endl;
cout<<ptr->perimeter()<<endl;

}
```
# Data Hiding
If we take an example of a car everything is hidden and only function of car is visible and through funcations we drive the car
 # Accessors and Mutators
 Property Function
- Accessor
 Getter Functions -> Read the value
- Mutators
  Setter Functions  -> Write the value
```cpp
class Rectangle{
private:
int length;
int breadth; 
public:
int area(){
return length*breadth;
}
int  perimeter(){
return 2*(length + breadth);
}

//We cannot access directly private member of a class in main function for accessing that we use set and get function

void setLength(int l){
//validate data
if(l>=0){
length=l;}
else
length=0;
}
void setBreadth(int b){
if(breadth>=0)
breadth=b;
else
breadth=0;
}
int getLength(){
return length;
}
int getBreadth(){
return breadth;
}
};

int main(){
Rectangle r;

//Set the private datamembers of class

r.setLength(10);
r.setBredth(5);

//for getting length

cout<<" Length of Rectangle" <<r.getLength()<<endl;
cout<<r.area();
}

```
# Constructors
already we have class Rectangle having length and breadth as data members , setter and getter for setting and accessing the value of length and breadth
- Why constructor:
            consider we buy a rectangle from bazar and we pay after paying we not decide the length and breadth, length and breadth are decided before paying
  same as in class we need to decide breadth and length during creation of object not after that, so constructor is best fit for this purpose a constructor call automatically when an object is created.
  # Rules
  - constructor have same name as class name
  - constructor has no any return type
 
  # Types of Constructor:
   - Default constructor
   - Non-parameterized constuctor
   - parametrized constructor
   - Copy constructor

  when an object is created  "default constructor" called automatically
default constructor is also sometimes called non-parametrized constructor or compiler provide constructor.
```cpp
// Non- parameterized constructor
Rectangle(){
length=0;
breadth=0;
}
int main(){
Rectangle r;
}

//parameterized constructor

Rectangle(int l, int b){
setLength(l);
setBreadth(b);
}

//Copy Constructor
Rectangle(Rectangle &rect){
length=rect.length;
breadth=rect.breadth;
}
//main function
int main(){
Rectangle r(10,15);
Rectangle r2(r);
}


```
# Deep Copy Constructor
```cpp

class Test{
int a;
int *p;
Test(int x){
 a=x;
  p=new int[a];
              }
Test(Test &t){
a=t.a;
p=t.p;
//it also point on same array of object r1 this is the problem with copy contructor so we need to create a new array for object r2 using deep copy constructor
p=new int[a];
}

};

//main
int main(){
Test t(5);
Test t2(t);
}

```




   
