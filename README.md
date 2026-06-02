# Custom Stack Library in C++ (LIFO Implementation)

A generic, high-performance **Stack Data Structure** library implemented in C++. This project demonstrates a deep understanding of Object-Oriented Programming (OOP) principles, specifically focusing on maximum **Code Reusability** and clean software architecture.

---

## 🚀 Key Feature: Masterful Code Reusability

Instead of reinventing the wheel and rewriting the core memory management or node manipulation logic, this **Stack** library is built entirely on top of an existing, custom-built **Queue/Doubly Linked List** (`clsMyQueue`). 

### How Reusability is Achieved:
* **Smart Inheritance:** `clsMyStack` inherits from `clsMyQueue<T>`. By leveraging the underlying structure, the Stack reuses existing tested methods seamlessly.
* **Conceptual Mapping (Abstraction):** * **`push()`** is achieved by reusing `InsertAtFront()` (or `InsertAtBeginning`).
  * **`top()`** cleanly maps to the queue's `front()`.
  * **`bottom()`** maps directly to the queue's `back()`.
* **Zero Redundancy:** This approach drastically reduces code duplication, minimizes potential bugs, and ensures that any optimization made to the base structure automatically enhances the Stack.

---

## 🛠️ Features

* **Generic Implementation:** Uses C++ Templates (`template <class T>`) to support any data type.
* **LIFO Logic:** Strict adherence to Last-In, First-Out behavior.
* **Clean & Readable Code:** Well-structured and adheres to modern C++ coding standards.

## 💻 Code Architecture Overview

```cpp
template <class T>
class clsMyStack : public clsMyQueue<T>
{
public:
    // Reusing Queue logic to implement Stack behavior
    void push(T Item) {
        clsMyQueue<T>::InsertAtFront(Item); 
    }
    
    T top() {
        return clsMyQueue<T>::front();
    }
    
    T bottom() {
        return clsMyQueue<T>::back();
    }
};
