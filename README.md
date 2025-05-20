# EX-26-AREA-OF-RECTANGLE-USING- POINTER
## AIM
To write a C Program to find area of rectangle using pointer.

## ALGORITHM
1.	Start the program.
2.	Read two numbers.
3.	Calculate the area of rectangle using the formula area=(x)(*y)
4.	Display the result.
5.	Stop the program.

## PROGRAM
```c
#include <stdio.h>

void calculateArea(int length, int breadth, int *area) {
    *area = length * breadth;
}

int main() {
    int length, breadth, area;

    printf("Enter length of rectangle: ");
    scanf("%d", &length);

    printf("Enter breadth of rectangle: ");
    scanf("%d", &breadth);

    calculateArea(length, breadth, &area);

    printf("Area of rectangle = %d\n", area);

    return 0;
}
```
## OUTPUT
![445637231-e2682eb0-e21a-4735-9164-86bb61223ffc](https://github.com/user-attachments/assets/f99157e4-e58a-46fe-9f36-b11e0eeedf04)
		       	


## RESULT
Thus the program to find area of rectangle using pointer has been executed successfully
 
 


# EX-27-DYNAMIC-MEMORY-ALLOCATION
## AIM
To write a C Program to print 'WELCOME' using malloc() and free().

## ALGORITHM
1.	Start the program.
2.	Read a string variable.
3.	Allocate memory using malloc().
4.	Display the string.
5.	Remove the allocated memory using free().
6.	Stop the program.

## PROGRAM
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    char *str;

    // Allocate memory for the string "WELCOME"
    str = (char *)malloc(8 * sizeof(char));

    // Check if memory allocation is successful
    if (str == NULL) {
        printf("Memory allocation failed\n");
        return -1;
    }

    // Copy the string "WELCOME" to the allocated memory
    sprintf(str, "WELCOME");

    // Print the string
    printf("%s\n", str);

    // Free the allocated memory
    free(str);

    return 0;
}
```
## OUTPUT
![445643387-b895b05b-f0a3-43c2-8b20-7bb629fd581d](https://github.com/user-attachments/assets/adf47ff6-41b9-488d-b8ac-1bf3fe6fb141)



## RESULT
Thus the program to print 'WELCOME' using malloc() and free() has been executed successfully
 
.



# EX-28-STUDENT-INFORMATION-USING-STRUCTURE

## AIM

To write a C Program to store the student information and display it using structure.

## ALGORITHM

1.	Start the program.
2.	Create a student structure with name, roll number and marks as members.
3.	Using structure variable read the structure members and print them.
4.	Stop the program.

## PROGRAM
```c
#include <stdio.h>
#include <string.h>

struct Student {
    int rollNo;
    char name[50];
    float marks;
};

int main() {
    struct Student student;

    printf("Enter roll number: ");
    scanf("%d", &student.rollNo);

    printf("Enter name: ");
    scanf("%*c"); // Consume newline character
    fgets(student.name, sizeof(student.name), stdin);
    student.name[strcspn(student.name, "\n")] = 0; // Remove newline character

    printf("Enter marks: ");
    scanf("%f", &student.marks);

    printf("\nStudent Information:\n");
    printf("Roll Number: %d\n", student.rollNo);
    printf("Name: %s\n", student.name);
    printf("Marks: %.2f\n", student.marks);

    return 0;
}
```

## OUTPUT
![445644118-d3b61441-3e5b-4552-810e-1fef4df3897c](https://github.com/user-attachments/assets/c3fb1f68-a048-48fd-97ff-8301548653d5)


## RESULT

Thus the program to store the student information and display it using structure has been executed successfully
 
 


# EX-29-EMPLOYEE-STRUCTURE-SALARY-CALCULATION

## AIM

To write a C Program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure.

## ALGORITHM

1.	Start the program.
2.	Create an employee structure with name, id and salary details as members.
3.	Using structure variable read the structure members.
4.	Calculate the gross salary and print the details.
5.	Stop the program.

## PROGRAM
```c
#include <stdio.h>

struct Employee {
    int id;
    char name[50];
    float basicSalary;
    float grossSalary;
};

void calculateGrossSalary(struct Employee *emp) {
    float da = 0.1 * emp->basicSalary; // 10% DA
    float hra = 0.2 * emp->basicSalary; // 20% HRA
    emp->grossSalary = emp->basicSalary + da + hra;
}

int main() {
    struct Employee employees[3];

    for (int i = 0; i < 3; i++) {
        printf("Enter employee %d's ID: ", i + 1);
        scanf("%d", &employees[i].id);

        printf("Enter employee %d's name: ", i + 1);
        scanf("%*c"); // Consume newline character
        fgets(employees[i].name, sizeof(employees[i].name), stdin);
        employees[i].name[strcspn(employees[i].name, "\n")] = 0; // Remove newline character

        printf("Enter employee %d's basic salary: ", i + 1);
        scanf("%f", &employees[i].basicSalary);

        // Calculate gross salary
        calculateGrossSalary(&employees[i]);
    }

    printf("\nEmployee Information and Gross Salary:\n");
    for (int i = 0; i < 3; i++) {
        printf("Employee ID: %d\n", employees[i].id);
        printf("Name: %s\n", employees[i].name);
        printf("Basic Salary: %.2f\n", employees[i].basicSalary);
        printf("Gross Salary: %.2f\n\n", employees[i].grossSalary);
    }

    return 0;
}
```

 ## OUTPUT
![445647093-0b6d9c4f-154d-491b-a662-8e5f396de847](https://github.com/user-attachments/assets/22a9098a-7764-4469-95be-4bea289d3dac)

 

## RESULT

Thus the C program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure
 




# EX – 30 -STUDENTS MARK -TOTAL &AVERAGE USING STRUCURE

## AIM
Create a C program to calculate the total and average of student using structure.

## ALGORITHM 

Step 1: Start the program.
Step 2: Define a struct student with:
•	name: a character array (size 10) for the student's name (not used in the logic).
•	rollno: an integer for the student's roll number (also unused).
•	subject[5]: an array to store marks of 5 subjects.
•	total: an integer to store total marks.
Step 3: Declare an array s[2] of type struct student for 2 students. Also declare variables n, i, and j for input 
             and iteration.
Step 4: Input Loop (i = 0 to 1):
•	Read an integer n (but it's not used later — possibly intended for roll number or placeholder).
•	Loop j = 0 to 4:
o	Read 5 subject marks into s[i].subject[j].
Step 5: Total Marks Calculation Loop (i = 0 to 1):
•	Initialize s[i].total to 0.
•	Loop j = 0 to 4:
o	Add each subject mark to s[i].total.
Step 6: Override Total (Hardcoded):
•	Set s[0].total = 374;
•	Set s[1].total = 383;
           This step overwrites the computed totals. It seems like testing or hardcoded totals — unnecessary if you’re 
                 already calculating them.
Step 7: Output Loop (i = 0 to 1):
•	Print s[i].total for each student.
Step 8: End the program.

## PROGRAM
```c
#include <stdio.h>

struct Student {
    int rollNo;
    char name[50];
    float marks[5];
    float total;
    float average;
};

void calculateTotalAndAverage(struct Student *student) {
    student->total = 0;
    for (int i = 0; i < 5; i++) {
        student->total += student->marks[i];
    }
    student->average = student->total / 5;
}

int main() {
    struct Student student;

    printf("Enter roll number: ");
    scanf("%d", &student.rollNo);

    printf("Enter name: ");
    scanf("%*c"); // Consume newline character
    fgets(student.name, sizeof(student.name), stdin);
    student.name[strcspn(student.name, "\n")] = 0; // Remove newline character

    printf("Enter marks for 5 subjects:\n");
    for (int i = 0; i < 5; i++) {
        printf("Subject %d: ", i + 1);
        scanf("%f", &student.marks[i]);
    }
    calculateTotalAndAverage(&student);

    printf("\nStudent Information:\n");
    printf("Roll Number: %d\n", student.rollNo);
    printf("Name: %s\n", student.name);
    printf("Total Marks: %.2f\n", student.total);
    printf("Average Marks: %.2f\n", student.average);

    return 0;
}

```

## OUTPUT
![445648587-b05f456e-1abc-43cc-999f-8a3e6d5c588d](https://github.com/user-attachments/assets/06bf0b39-d7ed-4693-97b0-e04c03d6010a)

 

## RESULT

Thus the C program to calculate the total and average of student using structure has been executed successfully.
	


