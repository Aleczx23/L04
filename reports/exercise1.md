# Bug reports for exercise1.py

Line: 3
Problem: The condition checks if n % 2 == 1, which is true for odd numbers, not even numbers. The function should return True for even numbers, so it should check if n % 2 == 0.
Example: is_even(4) returns False, expected True.
Fix: return n % 2 == 0

Line: 8
Problem: The function calculates the sum of width and height, but the docstring states it should return the area of a rectangle, which is width multiplied by height.
Example: rectangle_area(5, 3) returns 8, expected 15.
Fix: return width * height

Line: 13
Problem: The function is named "double" and should return twice the number, but it adds 2 instead of multiplying by 2.
Example: double(5) returns 7, expected 10.
Fix: return n * 2
