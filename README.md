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

p=NULL;

  
3. dangling pointer
    you are try to access the memory  when they are de-allocated
   
   
