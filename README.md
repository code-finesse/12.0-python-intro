# Python Intro

### **What is Python?**

Python is a high-level, general purpose programming language created by Guido van Rossum in 1991. It is currently the most used programming language. Python can be used for data science, devops, or general purpose programming. These notes will be focusing on using it as a server-side, "back-end" programming language.

As a backend language, Python does not have a GUI. 

## Interacting with Python

### **By File**

The first way that we can interact with Python is by running a Python file. Python files have the extension `.py` and can be run through the command line:

```python
cd sandbox/
mkdir py-test
cd py-test
touch app.py     # Create a Python file
python3 app.py   # Run that Python file
```

### **By REPL (Read-Evaluate-Print-Loop)**

The second way that we can interact with Python code is with a tools like IPython or the Python shell. These are both REPLs. Have we used these before?

```python
pip3 install ipython # install IPython
ipython               # start IPython REPL
exit                  # quit IPython
python3                # start Python3 REPL
exit()                # quit Python REPL
```

## Fundamental Characteristics of Python

- Everything in Python is an object
    - everything has its own set of properties and methods
- Variables
    - variables in Python are assigned by using a single equal sign (=)
    - variables are written in snake_case (all lower case with words separated by underscores)
    - variables are instantiated as they are used

    ```python
    my_favorite_animal = "Bengal Tiger"
    # => "Bengal Tiger"
    ```

- Numbers
    - Python uses similar arithmetic operators (+, -, *, /, %, **) to Javascript and has the same order of operations (P.E.M.D.A.S.)
    - there are integers and floats

    ```python
    1 + 2 # Addition
    # => 3

    6 - 5 # Subtraction
    # => 1

    5 * 2 # Multiplication
    # => 10

    30 / 5 # Division
    # => 6.0

    31 // 5 # Note: integer division
    # => 6

    30 % 5 # Modulo (remainder)
    # => 0

    31 % 5
    # => 1

    3 ** 2 # Exponentiation
    # => 9
    ```

- Strings
    - text just like in Javascript
    - surrounded by single or double quotes (double is customary)
    - Python uses similar escape characters
    - strings can be concatenated and multiplied

    ```python
    # Concatenation
    "Wassup " + "squad!"
    # => "Hello there!"

    # Multiplication
    "Wassup squad! " * 3
    # => "Hello there! Hello there! Hello there! "

    ```

    - strings can be interpolated multiple ways
        - format method takes the strings to be concatenated as its parameters
        - the clutchest (in my opinion) way is using an F string (new to python 3.6)

    ```python
    # FORMAT
    class_number = 22

    "I am teaching WDI {}.".format(class_number)
    # => "I am teaching WDI 22."

    person1 = "Spongbob"
    person2 = "Patrick"
    occupation = "frycook"
    print("{0} is a {2}. {1} is not.".format(person1, person2, occupation))# => "Lauren is a consultant. Frank is a consultant as well."
    # => "Spongebob is a frycook. Patrick is not.

    # F STRING
    city = 'Atlanta'
    print(f"Shout out to {city}")
    ```

- Booleans
    - they are True and False (both capitals)
    - comparison operators check for equality
        - the check for equality is always for both value and data type

        [Untitled](https://www.notion.so/eccd5453ba9b48d290a09f41eddaca1d)

    ```python
    num = 99
    0 < num < 100
    # => True
    ```

- Conditionals
    - No parentheses or curly brackets required
    - Begin blocks using `if`, `elif` and `else`
    - Use colons after each condition
    - Indentation matters! 4 spaces is the standard indent.

    ```python
    print("Welcome to the Iron Rattler! How tall are you (in feet)?")
    height = int(input("Enter your height in feet:"))

    if height < 4:
        print("Sorry you aren't tall enough")
    elif height < 7:
        print("Have fun!")
    else:
        print("If you value your head, you should not get on this ride.")
    ```

- Print and Input (input & output)
    - To print out to the console like console.log() does in JavaScript, we use the print function:

    ```python
    print("Hello, World!")
    # Hello, World!
    ```

    - Python also makes it easy for us to accept user input from the command line using input:

    ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/eda5d5ba-8a9c-4afa-9c45-49d436915d45/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/eda5d5ba-8a9c-4afa-9c45-49d436915d45/Untitled.png)

- Lists and Collections
    - An ordered collection of related values
    - Basically cooler arrays
    - Square brackets
    - Values separated by commas
    - Zero-indexed

    ```python
    numbers = [1, 2, 3]
    # => [1, 2, 3]

    animals = ["dog", "cat", "horse"]
    # => ["dog", "cat", "horse"]

    animals[0]
    # => "dog"

    animals[1] = "elephant"
    # => "elephant"

    animals
    # => ["dog", "elephant", "horse"]
    ```

    - more info

        ### **List Methods**

        Python provides us with an extensive library of list methods we can use to traverse and manipulate lists.

        - The Python [documentation](https://docs.python.org/3.6/tutorial/datastructures.html) for `List` is a great resource for learning more about these methods
        - Can't go over them all, but chances are if you could do it in JavaScript then you can do it in Python.

        > IMPORTANT: You DO NOT need to memorize these. The following is just a sample of array methods available to you. You'll come to be more familiar with these as you need them and look them up in documentation.tl;dr: The more you Google them, the better you'll remember them.

        ### **`.append()`, `.extend()`, and `.pop()`**

        - Append inserts an item into the end of the list.
        - Extend adds two arrays together.
        - Pop removes an item from the end of the list. You can also supply an index to `pop` to remove at that index.

        You can think of them in comparison to these equivalent javascript methods:

        [Untitled](https://www.notion.so/14f9ff4353a04faa9b0f68fe2467cb7b)

        ```python
        numbers = [1, 2, 3, 4, 5]
        # => [1, 2, 3, 4, 5]

        numbers.append(6)
        # => [1, 2, 3, 4, 5, 6]

        numbers.append([1, 2, 3])
        # => [1, 2, 3, 4, 5, 6, [1, 2, 3]]

        numbers.extend([7, 8, 9])
        # => [1, 2, 3, 4, 5, 6, [1, 2, 3], 7, 8, 9]

        numbers.pop()
        # => 9

        numbers
        # => [1, 2, 3, 4, 5, 6, [1, 2, 3], 7, 8]

        numbers.pop(0)
        # => [2, 3, 4, 5, 6, [1, 2, 3], 7, 8]
        ```

        Python also has a few methods that JS doesn't have:

        ### **`list.insert(index, value)`**

        Insert an item at a given position. The first argument is the index of the element before which to insert, so a.insert(0, x) inserts at the front of the list, and a.insert(len(a), x) is equivalent to a.append(x).

        ```python
        numbers = [3, 1, 5, 2, 4]

        numbers.insert(2, 11)

        # => [3, 1, 11, 5, 2, 4]
        ```

        ### **`sorted()`**

        Organizes list values from lowest to highest. Numbers and strings.

        ```python
        numbers = [3, 1, 5, 2, 4]
        # => [3, 1, 5, 2, 4]

        sorted(numbers)
        # => [1, 2, 3, 4, 5]
        ```

        ### **`.remove()`**

        - Removes an argument from a list
        - If there are multiple instances of that argument, it will delete just the first.

        ```python
        numbers = [3, 1, 2, 2, 4]
        # => [3, 1, 2, 2, 4]

        numbers.remove(2)
        # => 2

        numbers
        # => [3, 1, 2, 4]
        ```

- Dictionary
    - An unordered collection organized by key-value pairs
    - Basically cooler object

    ```python
    sei_class= {
      "teacher": "Jimmy",
      "students": ["Yacko", "Wacko", "Dot"],
      "classroom": 2,
      "in_session": True,
      "schedule": {
        "morning": "Python Basics",
        "afternoon": "Enumerables"
      }
    }

    # Accessing dictionary values:
    sei_class["teacher"]
    # => "John"

    # Note that you can't do this, like you can in javascript!
    sei_class.teacher

    # => AttributeError: 'dict' object has no attribute 'teacher'
    # Modifying dictionary values:

    sei_class["teacher"] = "Jimbo"
    # => "Jimbo"

    #Nested values:
    sei_class["schedule"]["morning"]
    # => "Python Basics"
    ```

    - more info

        ### **Dictionary Methods**

        Like lists, Python also provides us with a library of dictionary methods.

        - [Again, the Python documentation is a great resource](https://docs.python.org/3/tutorial/datastructures.html#dictionaries)

        > As mentioned with lists, do not worry about memorizing these methods. Just know how to look them up should the need arise.

        ### **Keys**

        Returns a `dict_keys` structure with all the keys in the dictionary. Can easily be translated to a list using `list()`.

        ```python
        sei_class.keys()
        # => dict_keys(['teacher', 'students', 'classroom', 'in_session', 'schedule'])

        list(sei_class.keys())
        # => ['teacher', 'students', 'classroom', 'in_session', 'schedule']
        ```

        Note that `dict_keys` is not a list. It's a specific data type, so it doesn't have all the same methods that lists have.

- Ranges
    - Parentheses
    - Min and max value - 1 inside `range`. Range is not inclusive, meaning that it includes numbers up until the second parameter but not the second parameter itself, similiar to using a `<` in for loops.
    - Generate list using `list()` function

    ```python
    list(range(1, 6))
    # => [1, 2, 3, 4, 5]

    #You can also use ranges in for loops!

    for i in range(1, 6):
      print(i)

    # => 1
    # => 2
    # => 3
    # => 4
    # => 5
    ```

    - more info

        ### **length**

        Python uses a special function called `len()` to get the length of different data structures.

        You can use `len()` on any iterable type, which includes lists and dictionaries.

        ```python
        sei_class = {
          "teacher": "John",
          "students": ["Yacko", "Wacko", "Dot"],
          "classroom": 2,
          "in_session": True,
          "schedule": {
            "morning": "Python Basics",
            "afternoon": "Enumerables"
          }
        }

        len(sei_class)
        # => 5
        ```

        > Note that there is no array.length property!

- Functions

    In Python, functions are defined like this:

    ```python
    def double(number):
        return number * 2
    ```

    - `def` - the Python equivalent of `function`
    - `double` - the function name in the above example
    - `number` - the parameter name in the above example
    - Use a `:` instead of curly brackets `{}`

    We invoke it like this:

    ```python
    double(3)
    # => 6
    ```

    You may have noticed that we use the same `return` notation as JavaScript.

    Python functions can also establish default argument values. In the below example, if we do not provide our `double` function with an argument, it will default to 5

    ```python
    def double(number=5):
        return number * 2

    double()
    # => 10
    ```

- Differences
    - Javascript

        ```jsx
        // Write a method that accepts a name from the user and then returns it. Here's the javascript:

        const getName = () => {
          let name = prompt("what is your name?");
          return name;
        };

        // Write a method that reverses a string. Here's the javascript:

        const reverseIt = () => {
          let string = "a man, a plan, a canal, frenemies!";

          let reverse = "";

          for (let i=0; i < string.length; i++) {
            reverse += string[string.length - (i+1)];
          };

          console.log(reverse);
        };

        // Write a method that swaps the values of two variables around. Here's the javascript:

        const swapEm = () => {
          let a = 10;
          let b = 30;
          let temp;

          temp = b;
          b = a;
          a = temp;

          console.log("a is now " + a + ", and b is now " + b);
        };

        // Write a method that multiplies all numbers in a given array and returns the final product. Here's the javascript:

        const multiplyArray = (ary) => {
          if (ary.length == 0) { return 1; };

          let total = 1;
          // let total = ary[0];

          for (let i=0; i < ary.length; i++) {
            total = total * ary[i];
          };

          return total;
        };

        // Write a method that takes a number argument and returns "fizz" if the number is divisible by three, "buzz" if the number is divisible by five, and "fizzbuzz" if it's divisible by both. Here's the javascript:

        const fizzbuzzer = (x) => {
          if( x%(3*5) == 0 ) {
            return 'fizzbuzz'
          } else if( x%3 == 0 ) {
            return 'fizz'
          } else if ( x%5 == 0 ) {
            return 'buzz'
          } else {
            return 'archer'
          }
        }

        // Write a method that finds the fibonacci number at the nth position and returns it. Here is the javascript:

        const nthFibonacciNumber = () => {
          let fibs = [1, 1];
          let num = prompt("which fibonacci number do you want?");

          while (fibs.length < parseInt(num)) {
            let length = fibs.length;
            let nextFib = fibs[length - 2] + fibs[length - 1];
            fibs.push(nextFib);
          }

          console.log(fibs[fibs.length - 1] + " is the fibonacci number at position " + num);
        };

        // Write a method that searches through an array for a value and returns true or false depending on whether or not the value is present in the array. Here is the javascript:

        const searchArray = (array, value) => {
          for(let i = 0; i < array.length-1; i++) {
            if(array[i] == value) {
              return true;
              break;
            }
          }
          return -1;
        };

        // Write a method that checks whether or not a string is a palindrome. Here is the javascript:

        const isPalindrome = (str) => {
          for(let i = 0; i < str.length/2; i++){
            if(str[i] != str[str.length-i-1]){
              return false;
              break;
            }
          }
          return true;
        };

        // Write a method that checks whether or not an array has any duplicates. Here is the javascript:

        const hasDupes = (arr) => {
          let obj = {};
          for (i = 0; i < arr.length; i++) {
            if(obj[arr[i]]) {
              return true;
            }
            else {
              obj[arr[i]] = true;
            }
          }
          return false;
        };
        ```

    - Python

        ```python
        def getName():
            name = input('what is your name? ')
            return name
        # print(getName())
        # Write a method that reverses a string.
        # # Option 1 using Slicing

        def reverseIt():
            string = 'a man, a plan, a canal, frenemies!'
            str_len = len(string)
            sliced_string = string[str_len::-1]
            return sliced_string
        # Option 2 Using a a while loop
        # def reverseIt():
        #     string = 'a man, a plan, a canal, frenemies!'
        #     reverse = ''
        #     index = len(string)
        #     while index > 0:
        #         reverse = reverse + string[index-1]
        #         index = index - 1
        #     return reverse
        # Option 3 Using join
        # def reverseIt():
        #     string = 'a man, a plan, a canal, frenemies!'
        #     reversed_string = ''.join(reversed(string))
        #     return reversed_string
        # print(reverseIt())
        # more javascript-like
        # def swap():
        #     a = 10
        #     b = 30
        #     temp = b
        #     b = a
        #     a = temp
        #     return f'a is now {a}, b is now {b}, and temp is now {temp}'
        # more pythonic

        def swap():
            a, b = 10, 30
            b, a = a, b
            return f'a is now {a} and b is now {b}'
        # print(swap())

        def multiply_array(arr):
            if len(arr) == 0:
                return 1
            product = 1
            for num in arr:
                product = product * num
            return product
        # print(multiply_array([1, 2, 5, 10, 5]))

        def fizz_buzzer(x):
            if x % 3 == 0 and x % 5 == 0:
                return 'fizzbuzz'
            elif x % 3 == 0:
                return 'fizz'
            elif x % 5 == 0:
                return 'buzz'
            else:
                return 'archer'
        # print(fizz_buzzer(2))

        def nth_fibonacci_number():
            fibs = [1, 1]
            num = input('which fibonacci number do you want? ')
            while len(fibs) < int(num):
                length = len(fibs)
                next_fib = fibs[length-2] + fibs[length-1]
                fibs.append(next_fib)
            return f'{fibs[len(fibs)-1]} is the fibonacci number at position {num}'
        # print(nth_fibonacci_number())
        # more javascript-like
        # def search_list(list, val):
        #     for item in list:
        #         if item == val:
        #             return True
        #     return False
        # more pythonic

        def search_list(list, val):
            return val in list
        # print(search_list(['cat', 'mouse', 'dog'], 'elephant'))

        def is_palindrome(str):
            if str == ''.join(reversed(str)):
                return True
            else:
                return False
        # # only works for single word strings
        # print(is_palindrome('noon'))
        # need to refactor so it accepts sentences

        def has_duplicates(list):
            for elem in list:
                if list.count(elem) > 1:
                    return True
            return False

        print(has_duplicates([1, 1, 3]))
        ```
