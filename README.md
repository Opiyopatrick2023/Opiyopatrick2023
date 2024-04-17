#include <stdio.h>
#include <string.h>


struct Student {

    char firstName[20];
    char lastName[20];
    char fullName[40];
    char hallOfResidence[50];
    int grades[4];
    char letterGrade;
};

int main() {
    struct Student student;


    printf("Enter first name: ");
    fgets(student.firstName,20,stdin);

    printf("Enter last name: ");
    fgets(student.lastName,20,stdin);

    printf("Enter hall of residence: ");
    fgets(student.hallOfResidence,50,stdin);

    printf("Enter 4 grades (separated by spaces): ");
    for (int i = 0; i < 4; ++i) {
        scanf("%d", &student.grades[i]);
    }


    int total = 0;
    for (int i = 0; i < 4; ++i) {
        total += student.grades[i];
    }
    float average = total / 4.0;


    if (average >= 80) {
        student.letterGrade = 'A';
    } else{ if (average >= 60) {
        student.letterGrade = 'B';
    } else {
        student.letterGrade = 'C';
    }}


    strcpy(student.fullName, student.firstName);
    strcat(student.fullName, " ");
    strcat(student.fullName, student.lastName);


    printf("\nFull Name: %s\n", student.fullName);
    printf("Hall of Residence: %s\n", student.hallOfResidence);
    printf("Grades: %d %d %d %d\n", student.grades[0], student.grades[1], student.grades[2], student.grades[3]);
    printf("Average Grade: %.2f\n", average);
    printf("Letter Grade: %c\n", student.letterGrade);

    return 0;
}
