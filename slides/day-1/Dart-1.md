## Dart Basics

Welcome to Day-1 of learning Dart basics! In this session, we will cover the fundamental concepts of Dart programming language. 
---

## Variables
Variables are used to store data values that can be used later in the program. In Dart, you can declare variables using the var, final, or const keyword.

```dart
var name = 'John'; // type inferred
final age = 30; // can't be reassigned
const PI = 3.14; // compile-time constant
```

### Types
Dart is a statically typed language, which means that each variable must have a specific type. Dart supports several built-in types, including int, double, String, bool, and more.

``` dart
int number = 10;
double decimal = 3.14;
String message = 'Hello World';
bool isTrue = true;
```
### Functions
Functions are a set of instructions that can be reused throughout the program. Dart supports two types of functions: named functions and anonymous functions (also known as lambda functions).

```dart

// Named Function
int sum(int a, int b) {
  return a + b;
}

// Anonymous Function
var product = (int a, int b) => a * b;

```

### Operators
Operators are symbols that perform operations on operands. Dart supports several types of operators, including arithmetic, comparison, logical, and bitwise operators.

```dart
int a = 10, b = 20;
print(a + b); // 30
print(a < b); // true
print(!(a < b)); // false
print(a & b); // 0
```

### If-Else

Conditional statements are used to execute different blocks of code depending on whether a condition is true or false. Dart supports if-else statements and ternary operators.

```dart
int age = 20;
if (age < 18) {
  print('You are not eligible to vote');
} else {
  print('You can vote');
}

// Ternary operator
age < 18 ? print('You are not eligible to vote') : print('You can vote');
```

### Loops
Loops are used to execute a block of code repeatedly. Dart supports for loops, while loops, and do-while loops.

``` dart
// for loop
for (var i = 1; i <= 10; i++) {
  print(i);
}

// while loop
int i = 1;
while (i <= 10) {
  print(i);
  i++;
}

// do-while loop
int j = 1;
do {
  print(j);
  j++;
} while (j <= 10);
```

### Lists
A list is a collection of elements in a specific order, where each element can be of any data type. In Dart, lists are represented using square brackets ([]) and can be created in several ways, such as:

```dart
List<String> names = ['John', 'Mary', 'Bob'];
List<int> numbers = [1, 2, 3, 4];
List<dynamic> mixed = [1, 'two', true];
```

#### Accessing Elements
You can access an element in a list by its index. In Dart, the index of the first element in a list is 0, and the index of the last element is length - 1. You can access an element using the square bracket notation ([]):

```dart
List<String> fruits = ['apple', 'banana', 'orange'];
print(fruits[0]); // apple
```

#### Adding Elements
You can add an element to the end of a list using the add method:

```dart
List<String> fruits = ['apple', 'banana', 'orange'];
fruits.add('grape');
print(fruits); // [apple, banana, orange, grape]
```

You can also add elements to a specific position in the list using the insert method:

```dart
List<String> fruits = ['apple', 'banana', 'orange'];
fruits.insert(1, 'grape');
print(fruits); // [apple, grape, banana, orange]
```

#### Removing Elements
You can remove an element from a list using the `remove` method:

```dart
List<String> fruits = ['apple', 'banana', 'orange'];
fruits.remove('banana');
print(fruits); // [apple, orange]
```

You can also remove an element at a specific position in the list using the removeAt method:

```dart
List<String> fruits = ['apple', 'banana', 'orange'];
fruits.removeAt(1);
print(fruits); // [apple, orange]
```

#### Updating Elements
You can update an element in a list by assigning a new value to it:

```dart
List<String> fruits = ['apple', 'banana', 'orange'];
fruits[1] = 'grape';
print(fruits); // [apple, grape, orange]
```

#### Important Functions
Dart provides several useful functions for working with lists. Here are some of the most commonly used functions:

1. `map`
    The `map` function applies a transformation function to each element of a list and returns a new list with the transformed elements. The transformation function takes an element of the list as input and returns a new value. Here's an example:

    ```dart
    List<int> numbers = [1, 2, 3, 4, 5];
    List<int> doubledNumbers = numbers.map((number) => number * 2).toList();
    print(doubledNumbers); // [2, 4, 6, 8, 10]
    ```
2. `where`
   The `where` function returns a new list that contains only the elements that satisfy a certain condition. The condition is specified by a boolean function that takes an element of the list as input and returns a boolean value. Here's an example:

    ```dart
    List<int> numbers = [1, 2, 3, 4, 5];
    List<int> evenNumbers = numbers.where((number) => number % 2 == 0).toList();
    print(evenNumbers); // [2, 4]
    ```

3. `reduce`
   The `reduce` function applies a binary function to the elements of a list in a cumulative way and returns a single value.

    ```dart
    List<int> numbers = [1, 2, 3, 4, 5];
    int sum = numbers.reduce((a, b) => a + b);
    print(sum); // 15
    ```



