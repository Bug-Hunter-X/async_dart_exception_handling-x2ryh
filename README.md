# Unhandled Exceptions in Asynchronous Dart Code

This repository demonstrates a common error in asynchronous Dart programming: failing to properly handle exceptions thrown within asynchronous operations.

The `bug.dart` file shows code that attempts to fetch data from an API but has incomplete exception handling.  The `bugSolution.dart` file provides a corrected version.

## Bug

The initial code lacks proper exception propagation.  While it catches exceptions in `fetchData`, the `catch` block only prints the error and doesn't re-throw the exception.  This means errors won't reach the error handling in the `main` function, causing unexpected behavior.

## Solution

The solution is to `rethrow` the exception in the `fetchData` function's `catch` block. This allows the exception to propagate to the `try-catch` block in `main`, where it can be handled appropriately.

This illustrates the importance of consistent exception handling in asynchronous Dart code to ensure robustness and avoid unexpected failures.