include <stdio.h>

typedef struct {
    double a;
    double b;
} Calculator;

// Function to perform addition operation
double add(Calculator *calc) {
    return calc->a + calc->b;
}

// Function to perform subtraction operation
double subtract(Calculator *calc) {
    return calc->a - calc->b;
}

// Function to perform multiplication operation
double multiply(Calculator *calc) {
    return calc->a * calc->b;
}

// Function to perform division operation
double divide(Calculator *calc) {
    if (calc->b == 0) {
        printf("Error: Cannot divide by zero.\n");
        return 0.0;
    }
    return calc->a / calc->b;
}

int main() {
    Calculator calc;
    double result;
    char operation;

    printf("Enter the first number: ");
    scanf("%lf", &calc.a);

    printf("Enter the second number: ");
    scanf("%lf", &calc.b);

    printf("Enter the type of operation (+ for Addition, - for Subtraction, * for Multiplication, / for Division): ");
    scanf(" %c", &operation);

    switch (operation) {
        case '+':
            result = add(&calc);
            break;
        case '-':
            result = subtract(&calc);
            break;
        case '*':
            result = multiply(&calc);
            break;
        case '/':
            result = divide(&calc);
            break;
        default:
            printf("Invalid operation selected.\n");
            return 1;
    }

    printf("Result: %lf\n", result);

    return 0;
}
