#include <stdio.h>
#include <string.h>

#define MAX_STUDENTS 50
#define NAME_LEN 50
#define PASS_MARKS 40.0

struct Student {
    int rollNo;
    char name[NAME_LEN];
    float marks;
};

void readLine(char str[], int size) {
    if (fgets(str, size, stdin) != NULL) {
        size_t len = strlen(str);
        if (len > 0 && str[len - 1] == '\n') {
            str[len - 1] = '\0';
        }
    }
}

int main() {
    struct Student students[MAX_STUDENTS];
    int n;

    printf("Enter number of students (1-%d): ", MAX_STUDENTS);
    if (scanf("%d", &n) != 1 || n < 1 || n > MAX_STUDENTS) {
        printf("Error: Invalid number of students.\n");
        return 1;
    }

    // Accept student details
    for (int i = 0; i < n; i++) {
        printf("\n--- Enter details for Student %d ---\n", i + 1);
        printf("Roll Number: ");
        if (scanf("%d", &students[i].rollNo) != 1) {
            printf("Error: Invalid roll number.\n");
            return 1;
        }
        getchar(); // Clear leftover newline from input buffer

        printf("Name: ");
        readLine(students[i].name, NAME_LEN);

        printf("Marks (0-100): ");
        if (scanf("%f", &students[i].marks) != 1 || students[i].marks < 0 || students[i].marks > 100) {
            printf("Error: Invalid marks.\n");
            return 1;
        }
    }

    // Display all student records with Pass/Fail result
    printf("\n%-10s %-25s %-10s %s\n", "Roll No", "Name", "Marks", "Result");
    printf("--------------------------------------------------------\n");
    for (int i = 0; i < n; i++) {
        const char *result = (students[i].marks >= PASS_MARKS) ? "PASS" : "FAIL";
        printf("%-10d %-25s %-10.2f %s\n",
               students[i].rollNo,
               students[i].name,
               students[i].marks,
               result);
    }

    return 0;
}
