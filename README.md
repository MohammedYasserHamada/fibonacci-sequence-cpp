/ fibonacci.cpp
#include <iostream>
using namespace std;

// دالة فيبوناتشي باستخدام التكرار (Iteration)
void FibonacciIterative(int terms) {
    int first = 0, second = 1, next;

    cout << "Fibonacci Sequence (Iterative):" << endl;
    for (int i = 0; i < terms; i++) {
        if (i <= 1)
            next = i;
        else {
            next = first + second;
            first = second;
            second = next;
        }
        cout << next << " ";
    }
    cout << endl;
}

// دالة فيبوناتشي باستخدام العودية (Recursion)
int FibonacciRecursive(int n) {
    if (n <= 1)
        return n;
    return FibonacciRecursive(n - 1) + FibonacciRecursive(n - 2);
}

void printFibonacciRecursive(int terms) {
    cout << "Fibonacci Sequence (Recursive):" << endl;
    for (int i = 0; i < terms; i++) {
        cout << FibonacciRecursive(i) << " ";
    }
    cout << endl;
}

int main() {
    int terms;

    cout << "Enter the number of terms: ";
    cin >> terms;

    if (terms <= 0) {
        cout << "Please enter a positive number." << endl;
        return 1;
    }

    FibonacciIterative(terms);
    printFibonacciRecursive(terms);

    return 0;
}
