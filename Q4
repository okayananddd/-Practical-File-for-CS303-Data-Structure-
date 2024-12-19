#include <stdio.h>

// Recursive function to calculate factorial
int factorial(int n) {
    printf("Entering state: n = %d\n", n); // Show stack state when entering a function call

    if (n == 0 || n == 1) { // Base case
        printf("Base case reached: n = %d\n", n);
        printf("Exiting state: n = %d, returning 1\n", n);
        return 1;
    }

    int result = n * factorial(n - 1);
    printf("Exiting state: n = %d, returning %d\n", n, result); // Show stack state when returning
    return result;
}

int main() {
    int num;

    printf("Enter a number to find its factorial: ");
    scanf("%d", &num);

    if (num < 0) {
        printf("Factorial is not defined for negative numbers.\n");
    } else {
        printf("\nCalculating factorial of %d using recursion:\n\n", num);
        int result = factorial(num);
        printf("\nFactorial of %d is %d\n", num, result);
    }

    return 0;
}
