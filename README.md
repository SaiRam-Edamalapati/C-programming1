# C-programming1

## **1. Maximum of Three Numbers**

### **Question**

Write a C program to find the maximum of three numbers without using logical operators.

### **Code**

```c
#include <stdio.h>
int main() {
    int a, b, c, max;

    printf("Enter three numbers: ");
    scanf("%d %d %d", &a, &b, &c);

    max = a;

    if (b > max)
        max = b;

    if (c > max)
        max = c;

    printf("Maximum number is: %d", max);

    return 0;
}
```

### **Output**

```
Enter three numbers: 10 25 15
Maximum number is: 25
```

---

## **2. Leap Year Check**

### **Question**

Write a C program to check whether a given year is a leap year or not. Also specify whether it is a century or non-century leap year.

### **Code**

```c
#include <stdio.h>
int main() {
    int year;

    printf("Enter a year: ");
    scanf("%d", &year);

    if (year % 400 == 0)
        printf("%d is a century leap year", year);
    else if (year % 100 == 0)
        printf("%d is a century non-leap year", year);
    else if (year % 4 == 0)
        printf("%d is a non-century leap year", year);
    else
        printf("%d is a non-century non-leap year", year);

    return 0;
}
```

### **Output**

```
Enter a year: 2024
2024 is a non-century leap year
```

---

## **3. Character Check**

### **Question**

Write a C program to check whether the entered character is alphabet, digit or special character. If alphabet, check whether it is vowel or consonant without using built-in functions.

### **Code**

```c
#include <stdio.h>
int main() {
    char ch;

    printf("Enter a character: ");
    scanf(" %c", &ch);

    if ((ch >= 'A' && ch <= 'Z') || (ch >= 'a' && ch <= 'z')) {
        printf("It is an alphabet\n");

        if (ch=='A'||ch=='E'||ch=='I'||ch=='O'||ch=='U'||
            ch=='a'||ch=='e'||ch=='i'||ch=='o'||ch=='u')
            printf("It is a vowel");
        else
            printf("It is a consonant");
    }
    else if (ch >= '0' && ch <= '9')
        printf("It is a digit");
    else
        printf("It is a special character");

    return 0;
}
```

### **Output**

```
Enter a character: A
It is an alphabet
It is a vowel
```

---

## **4. ATM Simulation**

### **Question**

Write a C program to implement a simple ATM simulation using switch statement with operations Check Balance, Deposit, Withdraw and Exit.

### **Code**

```c
#include <stdio.h>
int main() {
    int choice;
    float balance = 1000, amount;

    do {
        printf("\n1. Check Balance\n2. Deposit\n3. Withdraw\n4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch(choice) {
            case 1:
                printf("Balance: %.2f\n", balance);
                break;

            case 2:
                printf("Enter amount to deposit: ");
                scanf("%f", &amount);
                balance += amount;
                printf("Updated Balance: %.2f\n", balance);
                break;

            case 3:
                printf("Enter amount to withdraw: ");
                scanf("%f", &amount);
                if (amount <= balance) {
                    balance -= amount;
                    printf("Updated Balance: %.2f\n", balance);
                } else {
                    printf("Insufficient balance\n");
                }
                break;

            case 4:
                printf("Thank you!\n");
                break;

            default:
                printf("Invalid choice\n");
        }

    } while(choice != 4);

    return 0;
}
```

### **Output**

```
1. Check Balance
2. Deposit
3. Withdraw
4. Exit
Enter your choice: 1
Balance: 1000.00
```

---

## **5. Menu Driven Calculator**

### **Question**

Write a C program to implement a menu driven calculator using switch statement.

### **Code**

```c
#include <stdio.h>
int main() {
    int choice;
    float a, b;

    printf("1. Addition\n2. Subtraction\n3. Multiplication\n4. Division\n");
    printf("Enter your choice: ");
    scanf("%d", &choice);

    printf("Enter two numbers: ");
    scanf("%f %f", &a, &b);

    switch(choice) {
        case 1:
            printf("Result = %.2f", a + b);
            break;
        case 2:
            printf("Result = %.2f", a - b);
            break;
        case 3:
            printf("Result = %.2f", a * b);
            break;
        case 4:
            if (b != 0)
                printf("Result = %.2f", a / b);
            else
                printf("Division by zero not allowed");
            break;
        default:
            printf("Invalid choice");
    }

    return 0;
}
```

### **Output**

```
Enter your choice: 1
Enter two numbers: 5 3
Result = 8.00
```
