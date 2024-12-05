
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
open_account()
deposit_account()
withdraw()
check_bal()
apply_loan()

```









   
