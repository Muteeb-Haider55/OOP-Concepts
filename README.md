# OOP-Concepts
OOP BY Abdul-Bari
# Pointers
1. data variables   
2. address variables

   int x=10; //data variable
   int *p;    //address variable    declaration    
   p=&x;    //initialization
   cout<<*p; // dereferencing    output : 10

   # Why pointers
   a program can access code section and stack but program cannot
   be access the heap directly
   a program can access the heap indirectly using pointers

   int A[5]={1,2,3,4,5};  //this array is in stack section
   int *p;
   p=new int[5];  //new keyword is use to allcotes the memory in heap
   delete [] p;  // deallocates the memory when there is no need if we don't delete then it's cause of memory leakage

   # Pointers Arithmetic
    int A[5]={2,4,6,8,10};
   int *P=A;
   -Operations-
   1.    P++;//move to next location
  // How much bytes a pointer move is depends upon datatype of pointer integer pointer move two byte if initial address is 200 then next adress will be 202.

   2. P--; //move to backword
   3. P=P+2;
   4. P=P-2;
   5. d=P-Q; // Gives the difference between two pointers

   # Problem using Pointers

1. unintialized ptr
   e.g
   int *p;
   *p=25;
 or p=(int *)0x5638
2. memory leak

int *p=new int[5];

  
3. dangling pointer
    you are try to access the memory  when they are de-allocated
p=NULL;
# Reference 

  main()
  {
int x=10;
           //we cannot declare a refernece without initilization  it must be initilize at same time
int &y=x; // Referece
x++;
y++;
cout<<x; //11
cout<<y;  //12
   //refernce does not consume any memory here y is a refernce 
   //ones you initilize the y it connot be assign to any one again in the program
   cout<<&x<<"       "<<&y;      // Address of x and y will be same
   
  }
# Pointer of a Function

void display(){
cout<<"    HELLO    ";
}
int main(){
void(*fp)();

//Initilize a pointer to a function   During initlization we just write pointer name only in place of function name you just write pointer name in def of function 

fp=display;  // Assign a pointer to a function
(*fp)();     // Calling a pointer to a function
}


int max(int x,int x){
return x > y ? x : y;
}
int min(int x,int y){
return x < y ? x : y;
}
int main(){
int (*fp)(int,int);
fp=max;
(*fp)(10,5); // max function called
fp=min;
(*fp)(10,5); // min function called
// A function pointer assign all those function which have same signatures
// in polymorphisem functions use -function to a pointer- to achiving run time ploymorphisem


}




   
