# Java Methods and Return Values Example

A small Java program that demonstrates how to write a method that returns a value and how to call it from `main`.

## What It Demonstrates

The `Method` class has an `add` method that adds two numbers and returns the result:

```java
class Method {
    int add(int a, int b) {
        int c = a + b;
        return c;
    }
}
```

## Important: The Program Prints 0, Not 26

In the code, `main` creates an object of `MethodDemo`, not `Method`:

```java
MethodDemo t = new MethodDemo();
int m = t.add(10, 16);
```

So it calls the `add` method written at the bottom of `MethodDemo`, an auto-generated stub that always returns `0`:

```java
private int add(int i, int j) {
    // TODO Auto-generated method stub
    return 0;
}
```

The real `add` in the `Method` class is never used. Current output:

```
Result: 0
```

## The Fix

Create a `Method` object instead, and delete the auto-generated `add` stub from `MethodDemo`:

```java
public class MethodDemo {
    public static void main(String[] args) {
        Method t = new Method();
        int m = t.add(10, 16);
        System.out.println("Result: " + m);
    }
}
```

Output after the fix:

```
Result: 26
```

## Requirements

- Java Development Kit (JDK) 8 or higher

## Getting Started

### Clone the repository

```bash
git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>
```

### Compile

```bash
javac MethodDemo.java
```

### Run

```bash
java MethodDemo
```

## Key Concepts

- A method can return a value with `return`
- The return type (`int`) must match the type of the returned value
- You call a method on the object of the class that defines it
- IDE-generated `// TODO` stubs should be replaced with real code or removed

## Project Structure

```
.
├── MethodDemo.java
└── README.md
```

## Next Steps

- Add `subtract`, `multiply`, and `divide` methods
- Make `add` work with `double` values
- Take the two numbers from the user with `Scanner`
