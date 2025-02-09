# Subtle ARC Retain Cycle Bug in Objective-C

This repository demonstrates a common, yet often difficult to detect, memory leak in Objective-C due to a retain cycle caused by improper handling of strong references under Automatic Reference Counting (ARC).

## The Bug
The `bug.m` file contains the problematic code.  A `MyClass` instance is created, data is assigned to its strong `data` property, and then the `MyClass` instance is returned. Under specific circumstances, this can cause a retain cycle if the lifecycle of the object returned is not properly managed, leading to unexpected memory retention.

## The Solution
The `bugSolution.m` file demonstrates how to resolve the retain cycle.  This depends on the specific context in which the `MyClass` is used.  The fix usually involves carefully considering the ownership of the `data` object and potentially using weak references or carefully managing the object's lifecycle. 

## How to Reproduce
1. Clone this repository.
2. Open the project in Xcode.
3. Run the application.  (Observe memory usage for potential leaks if not resolved).

## Related Issues
* Memory leaks
* Unexpected object persistence
* ARC intricacies