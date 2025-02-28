# Arithmetic Formatter Project Documentation

## Overview
The **Arithmetic Formatter** project is designed to format basic arithmetic problems in a structured, easy-to-read vertical arrangement. This is particularly useful for primary school students learning to solve arithmetic problems.

The function, `arithmetic_arranger`, takes a list of arithmetic problems and optionally displays their solutions when a second argument is set to `True`.

## Function Signature
```python
arithmetic_arranger(problems: List[str], display_answers: bool = False) -> str
```

## Example Usage
### Function Call Without Solutions:
```python
arithmetic_arranger(["32 + 698", "3801 - 2", "45 + 43", "123 + 49"])
```
#### Output:
```
   32      3801      45      123
+ 698    -    2    + 43    +  49
-----    ------    ----    -----
```

### Function Call With Solutions:
```python
arithmetic_arranger(["32 + 8", "1 - 3801", "9999 + 9999", "523 - 49"], True)
```
#### Output:
```
  32         1      9999      523
+  8    - 3801    + 9999    -  49
----    ------    ------    -----
  40     -3800     19998      474
```

## Rules and Constraints

### Valid Input Requirements
- Each arithmetic problem must be in the format:
  ```
  operand1 operator operand2
  ```
- The operator can only be `+` or `-`.
- Operands must only contain digits.
- Each operand must be at most **four** digits wide.
- A maximum of **five** problems can be arranged at once.
- Problems should be arranged vertically, right-aligned.
- There should be four spaces between each formatted problem.
- Dashes (`-`) should run along the entire width of each problem.

### ❌ Error Handling
If the input does not meet the valid input requirements, the function returns an appropriate error message:

| Error Scenario | Error Message |
|---------------|----------------|
| More than five problems | `'Error: Too many problems.'` |
| Invalid operator (not `+` or `-`) | `'Error: Operator must be "+" or "-".'` |
| Non-numeric operand | `'Error: Numbers must only contain digits.'` |
| Operand exceeds four digits | `'Error: Numbers cannot be more than four digits.'` |

## Formatting Rules
1. **Alignment**:
   - Numbers must be right-aligned.
   - The operator must be placed between the two operands, aligned with the second operand.
   - The longest operand determines the width of the formatted problem.
2. **Spacing**:
   - Each problem is separated by four spaces.
   - A single space must be placed between the operator and the larger operand.
3. **Dash Lines**:
   - The dashes must match the width of the widest operand (including the operator and spacing).
4. **Solution Display** (Optional):
   - When enabled (`True` as the second argument), the solution is displayed beneath the dash line.

## Debugging and Testing
To see a more detailed output, open the browser console (`F12`). The function should be thoroughly tested with different input cases, including:
- Valid cases (correctly formatted problems)
- Edge cases (maximum number of problems, largest valid numbers)
- Invalid cases (errors due to incorrect input)

