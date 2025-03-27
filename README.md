# M426-Don't Repeat Yourself (DRY) :)

## **What is DRY?**

The **Don't Repeat Yourself (DRY)** principle is a software development concept that aims to **reduce code duplication**. It states that every piece of logic should have **a single representation** in the codebase.

## **Why Follow DRY?**

✅ **Easier Maintenance** – Changes need to be made in only one place.  
✅ **Fewer Bugs** – Reduces inconsistencies across the codebase.  
✅ **Better Readability** – Keeps the code clean and structured.  
✅ **Improved Scalability** – Easier to extend without redundant changes.

## **Bad Example**

Here, the Fibonacci logic is duplicated:

```js
function fibonacci(n) {
    if (n <= 0) return 0;
    if (n === 1) return 1;

    let a = 0, b = 1, temp;
    for (let i = 2; i <= n; i++) {
        temp = a + b;
        a = b;
        b = temp;
    }
    return b;
}

console.log("Fibonacci: ")

console.log(fibonacci(1))
console.log(fibonacci(2))
console.log(fibonacci(3))
console.log(fibonacci(4))
console.log(fibonacci(5))
console.log(fibonacci(6))
console.log(fibonacci(7))
console.log(fibonacci(8))
console.log(fibonacci(9))
```

## **Better Example**

Using a loop to eliminate redundancy:

```js
function fibonacci(n) {
    if (n <= 0) return 0;
    if (n === 1) return 1;

    let a = 0, b = 1, temp;
    for (let i = 2; i <= n; i++) {
        temp = a + b;
        a = b;
        b = temp;
    }
    return b;
}

console.log("Fibonacci: ")

for(let i = 1; i < 10; i++){
    console.log(fibonacci(i))
}
```

---

# **DRY & Design Patterns**

Applying **DRY** is closely related to using **Design Patterns**, as these patterns help eliminate redundancy and promote reusable, maintainable code.

## **Common Design Patterns Supporting DRY**

### **1. Singleton Pattern**

Ensures a class has only one instance, preventing redundant object creation.

```js
class Singleton {
    constructor() {
        if (!Singleton.instance) {
            Singleton.instance = this;
        }
        return Singleton.instance;
    }
}

const instance1 = new Singleton();
const instance2 = new Singleton();
console.log(instance1 === instance2); // true
```