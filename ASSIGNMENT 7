#include <stdio.h>
#include <string.h>

#define MAX_PATH 260

// Helper to read a filename safely without trailing newline
void readFilename(char str[], int size) {
    if (fgets(str, size, stdin) != NULL) {
        size_t len = strlen(str);
        if (len > 0 && str[len - 1] == '\n') {
            str[len - 1] = '\0';
        }
    }
}

int main() {
    char sourcePath[MAX_PATH], destPath[MAX_PATH];
    FILE *srcFile = NULL, *destFile = NULL;
    int ch;

    printf("Enter source file name: ");
    readFilename(sourcePath, MAX_PATH);

    printf("Enter destination file name: ");
    readFilename(destPath, MAX_PATH);

    // Prevent overwriting the source file with itself
    if (strcmp(sourcePath, destPath) == 0) {
        printf("Error: Source and destination files cannot be the same.\n");
        return 1;
    }

    // Open source file in read mode ("rb" handles both text and binary safely)
    srcFile = fopen(sourcePath, "rb");
    if (srcFile == NULL) {
        printf("Error: Could not open source file \"%s\".\n", sourcePath);
        return 1;
    }

    // Open destination file in write mode
    destFile = fopen(destPath, "wb");
    if (destFile == NULL) {
        printf("Error: Could not create destination file \"%s\".\n", destPath);
        fclose(srcFile);
        return 1;
    }

    // Copy character by character until End-Of-File (EOF)
    while ((ch = fgetc(srcFile)) != EOF) {
        if (fputc(ch, destFile) == EOF) {
            printf("Error: Failed while writing to destination file.\n");
            fclose(srcFile);
            fclose(destFile);
            return 1;
        }
    }

    printf("File copied successfully from \"%s\" to \"%s\".\n", sourcePath, destPath);

    // Close both file streams
    fclose(srcFile);
    fclose(destFile);

    return 0;
}
