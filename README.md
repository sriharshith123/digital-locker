#include <stdio.h>
#include <string.h>

#define PASSWORD "aeiceg" // Password to be matched

int main() {
    char matrix[3][3]; // 3x3 matrix
    char diagonal[4]; // Diagonal characters of the matrix
    int i, j, k = 0;

    // Accept input matrix
    printf("Enter the 3x3 matrix:\n");
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            scanf(" %c", &matrix[i][j]);
        }
    }

    // Concatenate diagonal characters
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            if (i == j || i+j == 2) {
                diagonal[k++] = matrix[i][j];
            }
        }
    }
    diagonal[k] = '\0'; // Add null character to terminate string

    // Check if password matches
    if (strcmp(diagonal, PASSWORD) == 0) {
        printf("Password verified!\n");
        if (diagonal[0] % 2 == 0) {
            printf("Even found\n");
        } else {
            printf("Odd found\n");
        }
    } else {
        printf("Incorrect password!\n");
    }

    return 0;
}
