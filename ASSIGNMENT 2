#include <stdio.h>

#define MAX 10

void readMatrix(int mat[MAX][MAX], int r, int c) {
    for (int i = 0; i < r; i++) {
        for (int j = 0; j < c; j++) {
            scanf("%d", &mat[i][j]);
        }
    }
}

void printMatrix(int mat[MAX][MAX], int r, int c) {
    for (int i = 0; i < r; i++) {
        for (int j = 0; j < c; j++) {
            printf("%d\t", mat[i][j]);
        }
        printf("\n");
    }
}

int main() {
    int a[MAX][MAX], b[MAX][MAX], res[MAX][MAX];
    int r1, c1, r2, c2, choice;

    printf("Matrix Operations:\n");
    printf("1. Addition\n2. Subtraction\n3. Multiplication\n4. Transpose\n");
    printf("Enter choice (1-4): ");
    scanf("%d", &choice);

    if (choice == 4) {
        printf("Enter rows and columns of the matrix: ");
        scanf("%d %d", &r1, &c1);
        printf("Enter elements of the matrix:\n");
        readMatrix(a, r1, c1);

        printf("\nTranspose:\n");
        for (int i = 0; i < c1; i++) {
            for (int j = 0; j < r1; j++) {
                printf("%d\t", a[j][i]);
            }
            printf("\n");
        }
        return 0;
    }

    printf("Enter rows and columns for Matrix A: ");
    scanf("%d %d", &r1, &c1);
    printf("Enter rows and columns for Matrix B: ");
    scanf("%d %d", &r2, &c2);

    switch (choice) {
        case 1: // Addition
        case 2: // Subtraction
            if (r1 != r2 || c1 != c2) {
                printf("Error: Dimensions must match for addition/subtraction.\n");
                return 1;
            }
            printf("Enter elements of Matrix A:\n");
            readMatrix(a, r1, c1);
            printf("Enter elements of Matrix B:\n");
            readMatrix(b, r2, c2);

            for (int i = 0; i < r1; i++) {
                for (int j = 0; j < c1; j++) {
                    res[i][j] = (choice == 1) ? (a[i][j] + b[i][j]) : (a[i][j] - b[i][j]);
                }
            }
            printf("\nResult:\n");
            printMatrix(res, r1, c1);
            break;

        case 3: // Multiplication
            if (c1 != r2) {
                printf("Error: Columns of A must equal rows of B.\n");
                return 1;
            }
            printf("Enter elements of Matrix A:\n");
            readMatrix(a, r1, c1);
            printf("Enter elements of Matrix B:\n");
            readMatrix(b, r2, c2);

            for (int i = 0; i < r1; i++) {
                for (int j = 0; j < c2; j++) {
                    res[i][j] = 0;
                    for (int k = 0; k < c1; k++) {
                        res[i][j] += a[i][k] * b[k][j];
                    }
                }
            }
            printf("\nProduct:\n");
            printMatrix(res, r1, c2);
            break;

        default:
            printf("Error: Invalid choice.\n");
    }

    return 0;
}
