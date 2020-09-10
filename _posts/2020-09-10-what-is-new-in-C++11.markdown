---
layout: post
title:  "What is new in C++11"
date:   2020-09-10 17:40::00
categories: blog
---

## What are the new features in C++ 11

- thread_local
  
    Below are some testing cases:

  - case1
    ```cpp
    class A {
    public: 
        A() {}
        ~A() {}

        void test(const std::string &name) {
            thread_local int count = 0;
            ++count;
            std::cout << name << ": " << coutn << std::endl;
        }    
    };

    void func(const std::string &name) {
        A a1;
        a1.test(name);
        a1.test(name);
        A a2;
        a2.test(name);
        a2.test(name);
    }

    int main(int argc, char* argv[]) {
        std::thread t1(func, "t1");
        t1.join();
        std::thread t2(func, "t2");
        t2.join();
        return 0;
    }
    ```
    output
    ```
    t1: 1
    t1: 2
    t1: 3
    t1: 4
    t2: 1
    t2: 2
    t2: 3
    t2: 4
    ```

  - case2
    ```cpp
    class A {
    public:
      A() {}
      ~A() {}

      void test(const std::string &name) {
        static int count = 0;
        ++count;
        std::cout << name << ": " <<  count << std::endl;
      }
    };

    void func(const std::string &name) {
      A a1;
      a1.test(name);
      a1.test(name);
      A a2;
      a2.test(name);
      a2.test(name);
    }

    int main(int argc, char* argv[]) {
      std::thread t1(func, "t1");
      t1.join();
      std::thread t2(func, "t2");
      t2.join();
      return 0;
    }
    ```
    output
    ```
    t1: 1
    t1: 2
    t1: 3
    t1: 4
    t2: 5
    t2: 6
    t2: 7
    t2: 8
    ```


