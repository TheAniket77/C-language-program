#include <stdio.h>

int main() {
    char operator;
    double num1, num2, result;

    // Prompt user for the operator
    printf("Enter an operator (+, -, *, /): ");
    scanf(" %c", &operator); // Note the space before %c to consume any trailing newline

    // Prompt user for the two numbers
    printf("Enter two numbers separated by a space: ");
    if (scanf("%lf %lf", &num1, &num2) != 2) {
        printf("Error: Invalid numeric input.\n");
        return 1;
    }

    // Perform calculation based on the operator
    switch (operator) {
        case '+':
            result = num1 + num2;
            printf("%.2lf + %.2lf = %.2lf\n", num1, num2, result);
            break;

        case '-':
            result = num1 - num2;
            printf("%.2lf - %.2lf = %.2lf\n", num1, num2, result);
            break;

        case '*':
            result = num1 * num2;
            printf("%.2lf * %.2lf = %.2lf\n", num1, num2, result);
            break;

        case '/':
            // Prevent division by zero runtime error
            if (num2 == 0) {
                printf("Error: Division by zero is not allowed.\n");
            } else {
                result = num1 / num2;
                printf("%.2lf / %.2lf = %.2lf\n", num1, num2, result);
            }
            break;

        default:
            printf("Error: '%c' is an invalid operator.\n", operator);
            break;
    }

    return 0;
}
