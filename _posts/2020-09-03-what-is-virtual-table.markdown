---
layout: post
title:  "What is virtual table"
date:   2020-09-03 16:17::00
categories: blog
---

## Example, more information in the comments
```cpp
class Base {
public:
    Base() {};
    virtual void f() { cout << "Base: f" << endl; };
    virtual void g() { cout << "Base: g" << endl; };
    void h() { cout << "Base: h" << endl; };
};

typedef void(*Fun) (void);

int main() {
    Base b;
    /*
    &b: the start address of object b
    (int*)&b: cast to int* type
    *(int*)&b: get the first 4 bytes, named vptr
    */
    cout << "virtual table address: " << *(int*)&b << endl; 
    /*
    vtable: consist of pFunc
    vptr: the start address of vtalbe
    (int*)*(int*)&b: cast to int* type
    *(int*)*(int*)&b: get the first 4 bytes, named first pFunc
    */
    cout << "fisrt virtual function address: " << *(int*)*(int*)&b << endl;
    cout << "second virtual function address: " << *((int*)*(int*)&b + 1) << endl;
}
```

## A note for pointer
int* p
* pointer type: int*
* the type to which the pointer points: int
* the value of pointer
* the memory addresss occupied by the pointer itself
