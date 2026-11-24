#include <stdio.h>

// Function to check leap year using Gregorian rules
int isLeapYear(int year) {
    if ((year % 4 == 0 && year % 100 != 0) || (year % 400 == 0)) {
        return 1; // Leap year
    }
    return 0; // Not a leap year
}

// Function to find the starting weekday of January 1st (0 = Sun, 6 = Sat)
int getFirstDayOfYear(int year) {
    int y = year - 1;
    return (1 + y + y / 4 - y / 100 + y / 400) % 7;
}

int main() {
    int year, choice, targetMonth;

    const char *monthNames[] = {
        "", "January", "February", "March", "April", "May", "June",
        "July", "August", "September", "October", "November", "December"
    };

    int daysInMonth[] = {0, 31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31};

    printf("Enter year (e.g., 2026): ");
    if (scanf("%d", &year) != 1 || year < 1) {
        printf("Error: Invalid year.\n");
        return 1;
    }

    // Apply leap year condition to update February days
    if (isLeapYear(year)) {
        daysInMonth[2] = 29;
        printf("%d is a Leap Year (February has 29 days).\n", year);
    } else {
        daysInMonth[2] = 28;
        printf("%d is NOT a Leap Year (February has 28 days).\n", year);
    }

    printf("\n1. Display Specific Month\n");
    printf("2. Display Full Year\n");
    printf("Enter choice (1-2): ");
    if (scanf("%d", &choice) != 1 || (choice != 1 && choice != 2)) {
        printf("Error: Invalid choice.\n");
        return 1;
    }

    if (choice == 1) {
        printf("Enter month (1-12): ");
        if (scanf("%d", &targetMonth) != 1 || targetMonth < 1 || targetMonth > 12) {
            printf("Error: Invalid month.\n");
            return 1;
        }
    }

    // Starting weekday for January 1st of the entered year
    int startDay = getFirstDayOfYear(year);

    for (int month = 1; month <= 12; month++) {
        // Print only if user chose full year OR this matches targetMonth
        if (choice == 2 || month == targetMonth) {
            printf("\n  ------------ %s %d ------------\n", monthNames[month], year);
            printf("  Sun  Mon  Tue  Wed  Thu  Fri  Sat\n");

            // Print leading spaces before the 1st day of the month
            for (int space = 0; space < startDay; space++) {
                printf("     ");
            }

            // Print all dates of the month
            for (int day = 1; day <= daysInMonth[month]; day++) {
                printf("%5d", day);
                if ((day + startDay) % 7 == 0) {
                    printf("\n");
                }
            }
            printf("\n");
        }

        // Advance startDay to the 1st day of the next month
        startDay = (startDay + daysInMonth[month]) % 7;
    }

    return 0;
}
