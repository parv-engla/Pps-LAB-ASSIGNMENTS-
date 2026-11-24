#include <stdio.h>
#include <string.h>
#include <ctype.h>

#define MAX 100

// Helper to read a full line safely without trailing newline
void readLine(char str[], int size) {
    if (fgets(str, size, stdin) != NULL) {
        size_t len = strlen(str);
        if (len > 0 && str[len - 1] == '\n') {
            str[len - 1] = '\0';
        }
    }
}

void reverseString(char str[]) {
    int left = 0;
    int right = strlen(str) - 1;
    while (left < right) {
        char temp = str[left];
        str[left] = str[right];
        str[right] = temp;
        left++;
        right--;
    }
}

int main() {
    char str1[MAX], str2[MAX], temp[MAX];
    int choice;

    printf("String Operations (using <string.h>):\n");
    printf("1. Length (strlen)\n");
    printf("2. Copy (strcpy)\n");
    printf("3. Concatenate (strncat)\n");
    printf("4. Compare (strcmp)\n");
    printf("5. Reverse\n");
    printf("6. Convert to Uppercase (toupper)\n");
    printf("7. Check Palindrome\n");
    printf("Enter choice (1-7): ");

    if (scanf("%d", &choice) != 1 || choice < 1 || choice > 7) {
        printf("Error: Invalid choice.\n");
        return 1;
    }
    getchar(); // Clear leftover newline from input buffer

    switch (choice) {
        case 1:
            printf("Enter a string: ");
            readLine(str1, MAX);
            printf("Length: %zu\n", strlen(str1));
            break;

        case 2:
            printf("Enter source string: ");
            readLine(str1, MAX);
            strcpy(str2, str1);
            printf("Copied string: %s\n", str2);
            break;

        case 3:
            printf("Enter first string: ");
            readLine(str1, MAX);
            printf("Enter second string: ");
            readLine(str2, MAX);
            // strncat prevents buffer overflow beyond MAX
            strncat(str1, str2, MAX - strlen(str1) - 1);
            printf("Concatenated string: %s\n", str1);
            break;

        case 4:
            printf("Enter first string: ");
            readLine(str1, MAX);
            printf("Enter second string: ");
            readLine(str2, MAX);
            int cmp = strcmp(str1, str2);
            if (cmp == 0) {
                printf("Strings are equal.\n");
            } else if (cmp < 0) {
                printf("\"%s\" comes before \"%s\".\n", str1, str2);
            } else {
                printf("\"%s\" comes after \"%s\".\n", str1, str2);
            }
            break;

        case 5:
            printf("Enter a string: ");
            readLine(str1, MAX);
            reverseString(str1);
            printf("Reversed string: %s\n", str1);
            break;

        case 6:
            printf("Enter a string: ");
            readLine(str1, MAX);
            for (int i = 0; str1[i] != '\0'; i++) {
                str1[i] = toupper((unsigned char)str1[i]);
            }
            printf("Uppercase string: %s\n", str1);
            break;

        case 7:
            printf("Enter a string: ");
            readLine(str1, MAX);
            strcpy(temp, str1);
            reverseString(temp);
            if (strcmp(str1, temp) == 0) {
                printf("\"%s\" is a palindrome.\n", str1);
            } else {
                printf("\"%s\" is not a palindrome.\n", str1);
            }
            break;
    }

    return 0;
}
