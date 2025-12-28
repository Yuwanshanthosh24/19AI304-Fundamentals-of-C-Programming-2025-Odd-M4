# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M4
# IAPR-4- Module 4 - FoC
## 7. Implementation of Functions.
## 8. Implementation of passing parameters.
# Ex.No:16
  Implement a C program to read a date in the format DD/MM/YYYY and determine whether the entered date is valid. The program should check the correctness of the day, month, and year, including leap year calculations for February.
# Date : 04/11/2025
# Aim:
 To implement a C program that validates a user-entered date using a function without parameters and without return value, ensuring the correctness of day, month, year, and leap year conditions.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3:
### Call the function `validateDate()`.
### Inside `validateDate()` function:
### Step 4: 
  Declare variables `dd`, `mm`, and `yy`.
### Step 5: 
  Ask the user to enter a date in `DD/MM/YYYY` format.
### Step 6: 
  Read the date values using `scanf`.
### Step 7: 
  Check if the year is between **1900 and 9999**.
 - If the year is invalid, display **"Year is not valid"** and stop further checks.
### Step 8: 
  Check if the month is between **1 and 12**.
- If the month is invalid, display **"Month is not valid"** and stop further checks.
### Step 9: 
  If the month has **31 days**, check if the day is between **1 and 31**.
### Step 10: 
  If the month has **30 days**, check if the day is between **1 and 30**.
### Step 11: 
  If the month is **February**:
  - Check if the day is between **1 and 28**, or if the day is **29**, verify if it's a **leap year**.
### Step 12: 
  If any valid condition is satisfied, display **"Date is valid."**
### Step 13: 
  Otherwise, display **"Date is invalid."**
### Step 14: 
  Stop
# Program:
```
#include <stdio.h>

// Function prototype
void validateDate();

int main()
{
    // Step 3: Call the function to validate date
    validateDate();
    return 0;
}

// Function definition
void validateDate()
{
    int dd, mm, yy;
    int isValid = 0; // Flag to check validity

    // Step 5 & 6: Input date
    printf("Enter date (DD/MM/YYYY): ");
    scanf("%d/%d/%d", &dd, &mm, &yy);

    // Step 7: Validate year
    if (yy < 1900 || yy > 9999)
    {
        printf("Year is not valid.\n");
        return;
    }

    // Step 8: Validate month
    if (mm < 1 || mm > 12)
    {
        printf("Month is not valid.\n");
        return;
    }

    // Step 9,10,11: Validate day based on month and leap year
    switch (mm)
    {
        case 1: case 3: case 5: case 7: case 8: case 10: case 12:
            if (dd >= 1 && dd <= 31)
                isValid = 1;
            break;
        case 4: case 6: case 9: case 11:
            if (dd >= 1 && dd <= 30)
                isValid = 1;
            break;
        case 2:
            // Leap year check
            if ((yy % 4 == 0 && yy % 100 != 0) || (yy % 400 == 0))
            {
                if (dd >= 1 && dd <= 29)
                    isValid = 1;
            }
            else
            {
                if (dd >= 1 && dd <= 28)
                    isValid = 1;
            }
            break;
    }

    // Step 12 & 13: Display result
    if (isValid)
        printf("Date is valid.\n");
    else
        printf("Date is invalid.\n");
}

```
# Output:
<img width="399" height="253" alt="image" src="https://github.com/user-attachments/assets/af6477c2-b410-4b9c-9fb9-44236d920181" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M4
# IAPR-4- Module 4 - FoC
# Ex.No:17
  Develop a C program to read two numbers from the user and determine the maximum and minimum values. Use user-defined functions with arguments and return values—one function to find the maximum (max()) and another to find the minimum (min()).
# Date :04/11/2025 
# Aim:
 To develop a C program that uses functions with parameters and return values to compute and display the maximum and minimum of two user-entered numbers.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare variables `num1`, `num2`, `maximum`, and `minimum`.
### Step 4: 
  Ask the user to enter two numbers.
### Step 5: 
  Read the numbers using `scanf`.
### Step 6: 
  Call the function `max(num1, num2)`.
### Step 7: 
  Inside function `max(num1, num2)`:
- **Step 7.1:** Receive two integer arguments.  
- **Step 7.2:** Compare the two numbers.  
- **Step 7.3:** If `num1 > num2`, return `num1`.  
- **Step 7.4:** Otherwise, return `num2`.
### Step 8: 
  Store the returned value in `maximum`.
### Step 9: 
  Call the function `min(num1, num2)`.
### Step 10: 
  Inside function `min(num1, num2)`:
- **Step 10.1:** Receive two integer arguments.  
- **Step 10.2:** Compare the two numbers.  
- **Step 10.3:** If `num1 > num2`, return `num2`.  
- **Step 10.4:** Otherwise, return `num1`.
### Step 11: 
  Store the returned value in `minimum`.
### Step 12: 
  Display the returned maximum and minimum values.
### Step 13: 
  Stop
# Program:
```
#include <stdio.h>

// Function prototypes
int max(int a, int b);
int min(int a, int b);

int main()
{
    int num1, num2;
    int maximum, minimum;

    // Step 4 & 5: Input two numbers
    printf("Enter two numbers: ");
    scanf("%d %d", &num1, &num2);

    // Step 6 & 8: Find maximum
    maximum = max(num1, num2);

    // Step 9 & 11: Find minimum
    minimum = min(num1, num2);

    // Step 12: Display results
    printf("Maximum = %d\n", maximum);
    printf("Minimum = %d\n", minimum);

    return 0;
}

// Step 7: Function to find maximum
int max(int a, int b)
{
    if (a > b)
        return a;
    else
        return b;
}

// Step 10: Function to find minimum
int min(int a, int b)
{
    if (a > b)
        return b;
    else
        return a;
}

```
# Output:
<img width="487" height="304" alt="image" src="https://github.com/user-attachments/assets/18d545ab-d166-4975-a2e9-9dd73b919f1b" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M4
# IAPR-4- Module 4 - FoC
# Ex.No:18
  Develop a C program to convert temperatures between Celsius and Fahrenheit: Convert Celsius to Fahrenheit using a function that returns the converted value. Convert Fahrenheit to Celsius using another function that returns the converted value. Display the results in the main() function.
# Date : 04/11/2025
# Aim:
 To develop a C program that converts temperatures between Celsius and Fahrenheit using functions with return values.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.  
### Step 3:
 Declare function prototypes:
 - `float celtof();`  
 - `float ftocel();`
### Step 4: 
  Enter the `main()` function.
### Step 5:
  Call the `celtof()` function to convert Celsius to Fahrenheit.
### Step 6: 
  Inside `celtof()` function:
 - Declare float variables `C` and `F`.  
 - Display the message: **"Enter the temperature in Celsius"**.  
 - Read the value of `C` from the user.  
 - Calculate Fahrenheit using the formula: `F = (C * 9 / 5) + 32`.  
 - Return `F` to `main()`.
### Step 7: 
  Print the returned Fahrenheit value in `main()`.
### Step 8: 
  Call the `ftocel()` function to convert Fahrenheit to Celsius.
### Step 9: 
  Inside `ftocel()` function:
 - Declare float variables `f` and `celsius`.  
 - Display the message: **"Enter the temperature in Fahrenheit"**.  
 - Read the value of `f` from the user.  
 - Calculate Celsius using the formula: `celsius = (f - 32) * 5 / 9`.  
 - Return `celsius` to `main()`.
### Step 10: 
 Print the returned Celsius value in `main()`.
### Step 11: 
 Stop
# Program:
```
#include <stdio.h>

// Step 3: Function prototypes
float celtof();   // Celsius to Fahrenheit
float ftocel();   // Fahrenheit to Celsius

int main()
{
    float F, C;

    // Step 5 & 7: Convert Celsius to Fahrenheit
    F = celtof();
    printf("Temperature in Fahrenheit: %.2f°F\n", F);

    // Step 8 & 10: Convert Fahrenheit to Celsius
    C = ftocel();
    printf("Temperature in Celsius: %.2f°C\n", C);

    return 0;
}

// Step 6: Function to convert Celsius to Fahrenheit
float celtof()
{
    float C, F;
    printf("Enter the temperature in Celsius: ");
    scanf("%f", &C);
    F = (C * 9 / 5) + 32;
    return F;
}

// Step 9: Function to convert Fahrenheit to Celsius
float ftocel()
{
    float f, celsius;
    printf("Enter the temperature in Fahrenheit: ");
    scanf("%f", &f);
    celsius = (f - 32) * 5 / 9;
    return celsius;
}

```
# Output:
<img width="481" height="313" alt="image" src="https://github.com/user-attachments/assets/2e0eb8dc-12cc-45f5-85da-5c2daa145708" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.

 
# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M4
# IAPR-4- Module 4 - FoC
# Ex.No:19
  Build a C program to print the elements of a given 4×4 matrix in spiral order starting from the top-left element and moving clockwise,using a user-defined parameterized function without return spiralPrint().
# Date : 04/11/2025
# Aim:
 To build a C program to display the elements of a 2D array in spiral form, traversing the outer elements first and then moving inward in a clockwise direction, using a user-defined parameterized function without return spiralPrint().
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.  
### Step 3: 
  Define constants `R` and `C` for the number of rows and columns in the matrix.
### Step 4: 
  Declare a function `spiralPrint(int m, int n, int a[R][C])` to print the matrix in spiral order.
### Step 5: 
  Inside `spiralPrint()` function:
 - Initialize variables:  
   - `k = 0` → starting row index  
   - `l = 0` → starting column index  
   - `m` → ending row index  
   - `n` → ending column index  
 - Repeat the following while `k < m` and `l < n`:
   - a. **Print the top row from left to right**:  
     - Loop from column `l` to `n-1` and print `a[k][i]`.  
     - Increment `k`.       
   - b. **Print the last column from top to bottom**:  
     - Loop from row `k` to `m-1` and print `a[i][n-1]`.  
     - Decrement `n`.       
   - c. **If `k < m`, print the bottom row from right to left**:  
     - Loop from column `n-1` to `l` and print `a[m-1][i]`.  
     - Decrement `m`.       
   - d. **If `l < n`, print the first column from bottom to top**:  
     - Loop from row `m-1` to `k` and print `a[i][l]`.  
     - Increment `l`.
### Step 6: 
  In the `main()` function:
- Declare and initialize a 4×4 matrix `a`.  
- Call `spiralPrint(R, C, a)` to print the elements in spiral order.
### Step 7: 
  Stop
# Program:
```
#include <stdio.h>

#define R 4
#define C 4

// Step 4: Function to print matrix in spiral order
void spiralPrint(int m, int n, int a[R][C])
{
    int i, k = 0, l = 0; // k = starting row, l = starting column

    // Step 5: Loop until all rows and columns are traversed
    while (k < m && l < n)
    {
        // a. Print the top row from left to right
        for (i = l; i < n; i++)
            printf("%d ", a[k][i]);
        k++;

        // b. Print the last column from top to bottom
        for (i = k; i < m; i++)
            printf("%d ", a[i][n - 1]);
        n--;

        // c. Print the bottom row from right to left
        if (k < m)
        {
            for (i = n - 1; i >= l; i--)
                printf("%d ", a[m - 1][i]);
            m--;
        }

        // d. Print the first column from bottom to top
        if (l < n)
        {
            for (i = m - 1; i >= k; i--)
                printf("%d ", a[i][l]);
            l++;
        }
    }
    printf("\n");
}

int main()
{
    // Step 6: Declare and initialize a 4x4 matrix
    int a[R][C] = {
        {1,  2,  3,  4},
        {5,  6,  7,  8},
        {9, 10, 11, 12},
        {13,14, 15,16}
    };

    // Call function to print in spiral order
    printf("Spiral order of the matrix:\n");
    spiralPrint(R, C, a);

    return 0;
}

```
# Output:
<img width="517" height="289" alt="image" src="https://github.com/user-attachments/assets/3c9a3fcd-e902-446f-9e9e-22b560433f51" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M4
# IAPR-4- Module 4 - FoC
# Ex.No:20
  Build a C program to convert a string such that the first and last characters, as well as the characters before and after each space, are converted to uppercase. Implement this using a user-defined parameterized function without return.
# Date : 04/11/2025
# Aim:
To build a C program to convert a string as described above, using a user-defined parameterized function without return convertFirstCLastC(char str[]).
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.  
### Step 3: 
  Declare a user-defined void function `convertFirstCLastC(char str[])` that takes the string as a parameter.
### Step 4: 
 Inside `convertFirstCLastC(char str[])` function:
 - Find the length of the string `len`.  
 - Convert the first character `str[0]` to uppercase.  
 - Loop through the string from index `1` to `len-2`:  
   - If a character is a space, capitalize the character before and after it.  
 - Convert the last character `str[len-1]` to uppercase.
### Step 5: 
 In `main()` function:
 - Declare a string `str[100]`.  
 - Read the input string from the user.  
 - Call the function `convertFirstCLastC(char str[])`.  
 - Print the modified string.
### Step 6: 
 Stop
# Program:
```
#include <stdio.h>
#include <ctype.h>
#include <string.h>

// Step 3: Function definition
void convertFirstCLastC(char str[])
{
    int len = strlen(str);

    if (len == 0)
        return;

    // Convert first character to uppercase
    str[0] = toupper(str[0]);

    // Loop through the string to capitalize characters around spaces
    for (int i = 1; i < len - 1; i++)
    {
        if (str[i] == ' ')
        {
            // Capitalize character before space
            if (i - 1 >= 0)
                str[i - 1] = toupper(str[i - 1]);
            // Capitalize character after space
            if (i + 1 < len)
                str[i + 1] = toupper(str[i + 1]);
        }
    }

    // Convert last character to uppercase
    str[len - 1] = toupper(str[len - 1]);
}

int main()
{
    char str[100];

    // Step 5: Read input string
    printf("Enter a string: ");
    scanf("%[^\n]", str);

    // Call the function to modify the string
    convertFirstCLastC(str);

    // Print the modified string
    printf("Modified string: %s\n", str);

    return 0;
}
```
# Output:
<img width="405" height="250" alt="image" src="https://github.com/user-attachments/assets/ce542d2c-0498-4242-a3f2-d54fcbe1de4e" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.

