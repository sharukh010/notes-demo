### Notes on Loops in Python

Loops in Python are used to execute a block of code repeatedly as long as a condition is met. There are two primary types of loops in Python: **`for` loops** and **`while` loops**. Understanding how to use these loops effectively can greatly simplify your code, especially when handling repetitive tasks.

#### 1. **`for` Loop**

A `for` loop is used to iterate over a sequence (such as a list, tuple, string, or range) and execute a block of code for each element in the sequence.

##### **Syntax:**

```python
for variable in sequence:
    # Code block to be executed
```

##### **Real-Life Example: Sending Emails to Customers**

Imagine you are managing a customer support team, and you need to send a follow-up email to every customer in a list.

```python
customers = ["Alice", "Bob", "Charlie", "David"]

for customer in customers:
    print(f"Sending follow-up email to {customer}")
```

**Explanation:**
- Here, `customers` is a list containing the names of the customers.
- The `for` loop iterates through each customer in the list and prints a message saying a follow-up email is being sent to that customer.

##### **Example 2: Calculating the Average Temperature**

Suppose you have a week's temperature data and want to calculate the average temperature.

```python
temperatures = [22, 24, 20, 21, 19, 23, 25]
total = 0

for temp in temperatures:
    total += temp

average = total / len(temperatures)
print(f"The average temperature for the week is {average:.2f}°C")
```

**Explanation:**
- `temperatures` is a list of temperature readings for a week.
- The loop iterates over each temperature, adding it to the `total`.
- After the loop ends, the average is calculated by dividing the `total` by the number of temperature readings.

##### **Example 3: Checking Attendance for a Class**

You are a teacher who needs to check if all students are present.

```python
students_present = ["John", "Emma", "Lucas", "Olivia"]
students_expected = ["John", "Emma", "Lucas", "Olivia", "Mia", "Liam"]

for student in students_expected:
    if student not in students_present:
        print(f"{student} is absent.")
```

**Explanation:**
- `students_present` is a list of students who are present.
- `students_expected` is a list of all students who should be in the class.
- The loop checks each expected student and prints the names of those who are absent.

#### 2. **`while` Loop**

A `while` loop continues to execute a block of code as long as a given condition is `True`.

##### **Syntax:**

```python
while condition:
    # Code block to be executed
```

##### **Real-Life Example: Countdown Timer**

Imagine you want to create a countdown timer that counts down from 10 to 1.

```python
countdown = 10

while countdown > 0:
    print(f"Countdown: {countdown}")
    countdown -= 1

print("Liftoff!")
```

**Explanation:**
- The variable `countdown` is initialized to 10.
- The `while` loop checks if `countdown` is greater than 0.
- If it is, the loop prints the current countdown value and then decrements it by 1.
- Once the countdown reaches 0, the loop ends, and "Liftoff!" is printed.

##### **Example 2: Input Validation**

You want to ensure a user enters a number greater than zero.

```python
number = int(input("Enter a number greater than zero: "))

while number <= 0:
    print("Invalid input. Please enter a number greater than zero.")
    number = int(input("Enter a number greater than zero: "))

print(f"Thank you! You entered: {number}")
```

**Explanation:**
- The user is prompted to enter a number.
- The `while` loop checks if the number is less than or equal to zero.
- If the condition is met, it prints an error message and prompts the user again until a valid number is entered.

##### **Example 3: Monitoring Battery Level**

Consider an IoT device that checks its battery level and sends an alert when it falls below 20%.

```python
battery_level = 100  # Initial battery level

while battery_level > 20:
    print(f"Battery level is at {battery_level}%. No action needed.")
    battery_level -= 5  # Simulating battery usage

print("Battery level critical! Please recharge.")
```

**Explanation:**
- The initial `battery_level` is set to 100%.
- The `while` loop checks if the battery level is above 20%.
- If it is, the loop prints a message and decreases the battery level by 5% (simulating usage).
- Once the battery falls to or below 20%, an alert message is displayed.

#### **Combining `for` and `while` Loops**

Sometimes, you may need to use both `for` and `while` loops to handle more complex scenarios.

##### **Example: Automated Sales Reporting**

Imagine a situation where you run a small business and want to generate a sales report for each salesperson. You will continue generating reports until all data is processed.

```python
sales_data = {
    "John": [200, 300, 250],
    "Emma": [400, 500],
    "Lucas": [100, 150, 200, 100],
}

for salesperson, sales in sales_data.items():
    total_sales = 0
    i = 0
    
    while i < len(sales):
        total_sales += sales[i]
        i += 1
    
    print(f"Total sales for {salesperson}: ${total_sales}")
```

**Explanation:**
- `sales_data` is a dictionary where each key is a salesperson, and the values are their sales amounts.
- The `for` loop iterates through each salesperson.
- Inside the loop, a `while` loop calculates the total sales for each salesperson by iterating over their sales data.

#### **Conclusion**

Loops are fundamental in programming, enabling repetitive tasks to be performed efficiently. By using `for` loops to iterate over sequences and `while` loops to repeat actions until a condition is met, you can manage a wide range of real-life scenarios like email notifications, data analysis, input validation, and more.