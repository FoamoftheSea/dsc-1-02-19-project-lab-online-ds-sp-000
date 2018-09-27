
## Project: Develop a Basic calculator program using Python

### SWABT

* Show mastery of the content covered in this section including:
        1. Data types 
        2. Iteration 
        3. Conditionals 
        4. Functions 
        5. User I/O. 

### The problem

>**Create a simple calculator which can perform basic arithmetic operations like addition, subtraction, multiplication or division depending upon the user input**.

### Approach 

* User choose the desired operation. Options 1, 2, 3, 4 are valid options for operations.  
* Two numbers are taken and an `if…elif…else` branching is used to execute a particular section.

* Using functions `add()`, `subtract()`, `multiply()` and `divide()` evaluate respective operations.

* The code should handle exceptions and must return **"invalid input*** when an unexpected character is given in the input (anything other than 1 - 4).

### Example Interface

Here is the interface you are expected to build. Don't worry if it is not 100% exactly as what is shown. Focus more on the getting the logic correct at this stage. 

```
Please select an operation:
1. Add
2. Subtract
3. Multiply
4. Divide

Select operations form 1, 2, 3, 4 : 1
Enter first number : 20
Enter second number : 13
20 + 13 = 33
```

### Creating Arithmatic Functions

We shall create four functions, one for each arithmatic operation which will perform the required operation and resturn the resulting value as shown below:


```python
# Function to add two numbers 
def add(num1, num2):
    return num1 + num2
```


```python
# Function to subtract two numbers 
def subtract(num1, num2):
    return num1 - num2
```


```python
# Function to multiply two numbers
def multiply(num1, num2):
    return num1 * num2
```


```python
# Function to divide two numbers
def divide(num1, num2):
    return num1 / num2
```

### Create a Command-line User Interface
We shall now write the main program body to take user input and call the relevent function


```python
# Print user menu 
print("Please select operation -\n" \
        "1. Add\n" \
        "2. Subtract\n" \
        "3. Multiply\n" \
        "4. Divide\n")

# Take input from the user for operation , followed by numbers. 
select = input("Select operations form 1, 2, 3, 4 :")
 
number_1 = int(input("Enter first number: "))
number_2 = int(input("Enter second number: "))

# Based on operation, pass the two numbers to respective function
# Print the output in a nice manner
# Print "Invalid input" if an unexpected character is seen in input
if select == '1':
    print(number_1, "+", number_2, "=",
                    add(number_1, number_2))
 
elif select == '2':
    print(number_1, "-", number_2, "=",
                    subtract(number_1, number_2))
 
elif select == '3':
    print(number_1, "*", number_2, "=",
                    multiply(number_1, number_2))
 
elif select == '4':
    print(number_1, "/", number_2, "=",
                    divide(number_1, number_2))
else:
    print("Invalid input")
    

# Expected output    

# Please select operation -
# 1. Add
# 2. Subtract
# 3. Multiply
# 4. Divide

# Select operations form 1, 2, 3, 4 :1
# Enter first number: 2
# Enter second number: 3
# 2 + 3 = 5
```

    Please select operation -
    1. Add
    2. Subtract
    3. Multiply
    4. Divide
    
    Select operations form 1, 2, 3, 4 :1
    Enter first number: 2
    Enter second number: 3
    2 + 3 = 5


## Bring in the While loop

We can see how the logic set by using if-else statements, along with functions can be used to control the flow of the program in an easy way. Let's add more functionality to our calculator as below:

>Lets try to make it a bit more interesting by introducing the behaviour of a real calculator so our users can choose to either continue with calculationa OR exit the system. Users gets this functionality by pressing `y` for yes and `n` for no towards continuation.

### Example Interface

Notice `continue: y/n` at the bottom of interface.

```
Please select an operation:
1. Add
2. Subtract
3. Multiply
4. Divide

Select operations form 1, 2, 3, 4 : 1
Enter first number : 20
Enter second number : 13
20 + 13 = 33

Continue: y/n
```

Let's work towards implementing iteration into the equation and enclose above I/O interface inside a while loops.


```python
# Initialize the code with cont (continue) flag set to yes (y)
cont = 'y'

# Check for user input after each iteration of the code
while cont == 'y':

        # Run the code block as above
        
        select = input("Select operations form 1, 2, 3, 4 :")
     
        number_1 = int(input("Enter first number: "))
        number_2 = int(input("Enter second number: "))
 
        if select == '1':
            print(number_1, "+", number_2, "=",
                    add(number_1, number_2))
 
        elif select == '2':
            print(number_1, "-", number_2, "=",
                    subtract(number_1, number_2))
 
        elif select == '3':
            print(number_1, "*", number_2, "=",
                    multiply(number_1, number_2))
 
        elif select == '4':
            print(number_1, "/", number_2, "=",
                    divide(number_1, number_2))
            
        # Prompt user for input if he/she wants to repeat 
        
        cont = input("Continue? y/n:")
        if cont == "n":
            break

#Expected output format

# Select operations form 1, 2, 3, 4 :4
# Enter first number: 5
# Enter second number: 4
# Press d for division and m for modulo operatorm
# 5 / 4 = 1
# Continue? y/n:y
# Select operations form 1, 2, 3, 4 :4
# Enter first number: 5
# Enter second number: 4
# Press d for division and m for modulo operatord
# 5 / 4 = 1.25
```

    Select operations form 1, 2, 3, 4 :4
    Enter first number: 5
    Enter second number: 4
    Press d for division and m for modulo operatorm
    5 / 4 = 1
    Continue? y/n:y
    Select operations form 1, 2, 3, 4 :4
    Enter first number: 5
    Enter second number: 4
    Press d for division and m for modulo operatord
    5 / 4 = 1.25


## Level up (Optional)

The while loop shown above allows the iteration through the code until a specific input from user i.e. `n` is noticed. Let's add some more functionality to this code by asking users about the type of division they are interested in, and this could be either normal division (as before) or a modulo operator (shows remainder).

>Change the code in the division function so that if a user selects division operation, the code should ask the user if he/she wants a normal division `/` (int) or `//` (float) , or a module `%` operator which only returns the remainder of a division. The program should return an exception for any other inputs. 


```python
def divide(num1, num2):
    div = input('Press d for division and m for modulo operator')
    if div == 'd':
        return num1 / num2
    elif div == 'm':
        return num1 % num2
    else:
        print ("Invalid input")
    return None

```

### Summary

In this lab we saw how loops and conditions can be used to control the logic of a program execution based on user input. We started with building a simple calculator and incrementaly added more functionality to it by adding loops for iteration and further conditions allowing different type of calculations. We also practiced User I/O by taking choices from the users and dealing with exceptions (unexpected input). 
