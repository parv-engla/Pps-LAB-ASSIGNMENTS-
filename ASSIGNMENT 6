#include <stdio.h>

// Function to swap two numbers using pointers (Call by Reference)
void swap(double *a, double *b) {
    if (a == NULL || b == NULL) {
        return;
    }
    double temp = *a;
    *a = *b;
    *b = temp;
}

int main() {
    double num1, num2;

    printf("Enter first number: ");
    if (scanf("%lf", &num1) != 1) {
        printf("Error: Invalid input.\n");
        return 1;
    }

    printf("Enter second number: ");
    if (scanf("%lf", &num2) != 1) {
        printf("Error: Invalid input.\n");
        return 1;
    }

    printf("\nBefore Swapping:\n");
    printf("First number  = %.2lf\n", num1);
    printf("Second number = %.2lf\n", num2);

    // Pass addresses of num1 and num2 to swap()
    swap(&num1, &num2);

    printf("\nAfter Swapping:\n");
    printf("First number  = %.2lf\n", num1);
    printf("Second number = %.2lf\n", num2);

    return 0;
}
