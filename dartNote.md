# Data Types
- bool
    * checks if an item is true of false
        ```dart
        bool isBool = true;
        ```
<br />

- double
    * used when a variable isn't a whole number
        ```dart
        double notWhole = 3.142;
        ```
<br />

- int
    * used for an actual whole number
        ```dart
        int wholeNumber = 20;
        ```
<br />

- var
    * used to invoke type infarction (automatically gets the type)
        ```dart
        var idkType = 20;
        ```
<br />

- num
    * this acts both in place of double and int
        ```dart
        num number = pi;
        print(number.toStringAsFixed(3));
        ```
<br />

- const
    * used to invoke type infarction (automatically gets the type) only this time it's constant and can't be changed
        ```dart
        const wholeNumber = 20;
        ```
<br />

- final
     * used to invoke type infarction (automatically gets the type) only this time it's constant and can't be changed much like the const but it's used when a value isn't known till run time
        ```dart
        const power = pow(2, 22);
        ```
<br />

- dynamic
    * this it used when you want to `Dynamically` change the value of a variable
        ```dart
        dynamic changingValue = 2;
        changingValue = "apple";
        ```
<br />
        
# Null check
you can use the following for null checks
- .?
    ```dart
    class Number {
    int num = 20;
    }

    void main() {
    var number;
    var numberClass = Number();
    print(numberClass.num);
    print(number?.num??"apple");
    }
    // we're checking if number.num is null and since num doesn't exist in number and number is a null field we can add the ?? operator as a sorta fall back
    ```
- ??= 
    ```dart
    void main() {
    var number;
    print(number ??= 100);
    print(number);
    }
    // if a value is null it assigns it to the number 100
    ```
<br />

# Type checking
- you can check types using the is statement

    ```dart
    void main() {
    var data = 10.98;
    if (data is double) {
        print("yes ");
    } else {
        print("no");
    }
    }
    ```
<br />

# Lists
- you can create a list in dart by simply using a square brackets, there are multiple ways to do so

    ```dart
    List <String> letters = ["s", "h"];
    ```
    
    -  Here we used a `List` indicator and assigned it to `String` since our list comprises mainly of strings, you can also put in `dynamic` or `int` or `bool` or `num` if the list consists of the respective types only
    <br>
    
    ```dart
    var letters = ["s", "h", "a"]
    ```
    -  we can also use the var keyword along with `const` and `final` since all these do type infraction so the type `List` is generated automatically
    
    ```dart
    List <String> names = const ["peter", "paul"];
    ```
    -  you can make a list a constant unchanging by adding the `const` keyword
<br />  
  
# Loops
- you can create a loop in essentially 3 ways `for`, `for in` and `for each` loops
    - for loop
        ```dart
        List <String> people = [
            "james",
            "John",
            "paul",
            "Samson"
        ]
        for (var i; i < people.length; i++){
            String person = people[i];
            print(person);
        }
        ```
        
    - for in loop
    
        ```dart
         List <String> people = [
            "james",
            "John",
            "paul",
            "Samson"
        ]
        for (var person in people){
            print(person);
        }
        ```
    - for each loop
    
        ```dart
        List <String> people = [
            "james",
            "John",
            "paul",
            "Samson"
        ]
        people.forEach((person)=>{
            print(person)
        });
        
        List<String> names = ['john', 'paul', 'peter'];
        names.forEach((element) {
            print(element);
        });
        ```

    - while loop
        ```dart
        int count = 0;
        List <String> people = [
            "james",
            "John",
            "paul",
            "Samson"
        ]
        while (count < people.length){
            String person = people[count];
            print(person);
        }
        ```
        a while loop executes everything as long as a condition is true, once the condition becomes false the loop stops

    -   do while

        ```dart
        int count = 0;
        do {
            print('this is count number $count');
        } while (count != 0);
        ```

        a do while loop basically makes sure that the expression or code inside the do loop would be executed at least once regardless of whether it's while block is true or false
    
# Sets
- sets are unordered data type which have unique values hence two or more items of a set can't repeat
    ```dart
    void main() {
    Set<String> set = {
        "apple",
        "avocado",
        "pear",
        "eggplant"
    };
    print(set);
    }

    ```

# Maps
- maps are like dictionaries and their values are gotten by a bracket notation
    ```dart
    Map<String, dynamic> map = {"apple": "fruit", "one": 1};
    print(map["apple"]);
    ```
    in a map you'd have to set the key and value of it

# functions
- in dart functions can be created this way
    ```dart
    returnType functionName(parameterType parameter){
        code block
    }
    ```
    if a function returns nothing it's return type should be void else it should be it's return type `bool`, `int`, `num`, `double`, `String` e.t.c.
    There are different types of functions, arrow function, anonymous functions and named functions
    -  named functions
        ```dart
        void greeting(String name){
            return 'hello $name';
        }
        ```
    - anonymous
        ```dart
        (String name){
            return 'hello $name';
        }
        ```
    - arrow functions
        ```dart
        int squared(number) => number*number;
        ```
     in dart we can also change from positional/optional arguments to non positional arguments by adding a curly braces in our parameter, if nothing is given as a parameter it will evaluate to `null`
     
     ```dart
    print(addNumbers(number1: 20, number2: 30));
    print(addNumbers(number2: 10, number1: 90));
    dynamic addNumbers({number1, number2}) {
        return number1 + number2;
    }
     ```
     incase of null return fear you can add null aware operators which give a default value fo exampling adding zero as the fall back if it's null
    ```dart
    dynamic addNumbers({number1, number2}) {
        return (number1 ?? 0) + (number2 ?? 0);
    }
    ```
    aside from using a null aware you can also give it a default parameter 
    ```dart
    dynamic addNumbers({number1, int number2 = 10}) {
        return (number1 ?? 0) + (number2 ?? 0);
    }
    ``` 
    if you were to use a square bracket instead of a parentheses the value in the square bracket would be optional too except that you won't have to do parameterName: value
    ```dart
    addNumbers(10, 20);
    addNumbers(40);
     dynamic addNumbers(number1, [int number2 = 10]) {
        return number1 + number2;
    }
    ```

# Classes
- classes
```dart
class Person {
  String? name;
  int? age;

  Person(String name, [int? age]) {
    this.name = name;
    this.age = age;
    if (age != null && age % 2 == 0) {
      print("you're an even age");
    } else {
      print("You're an odd age");
    }
  }

  Person.guest() {
    name = "James";
    age = this.age;
  }

  void showOutput() {
    print("your name is $name");
    print("you're $age years old");

    if (age != null) {
      print(age! + 2);
    } else {
      print("age is null");
    }
  }
}

void main() {
  Person person1 = Person('Tobi', 30);
  Person person2 = Person.guest();
  person1.age = 17;
  person1.showOutput();
  person2.showOutput();
}
```
- Person.guest() is a constructor while the person inside the class person is a default constructor 
- Read more on OOP in dart!