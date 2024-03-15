# Technical Debt

In this section, we'll examine different types of technical debt present in our codebase.

## Function with Architecture Flaws:

```c
/**
 * This function calculates the area of a rectangle.
 * @param length The length of the rectangle.
 * @param width The width of the rectangle.
 * @return The area of the rectangle.
 */
double calculateRectangleArea(double length, double width) {
    // Calculate area
    return length * width;
}
