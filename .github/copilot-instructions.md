# AI Agent Instructions for Scientific Calculator

## Project Overview
This is a single-page scientific calculator application built with vanilla HTML, CSS, and JavaScript. The calculator supports advanced mathematical operations including trigonometric functions, logarithms, and constants like π and e.

## Key Files and Structure
- `index.html`: Contains the entire application including HTML structure, CSS styles, and JavaScript functionality
  - HTML section (lines 1-99): Defines calculator UI and button layout
  - CSS section (lines 7-29): Defines calculator styling with CSS variables
  - JavaScript section (lines 100-213): Implements calculator logic

## Core Functionality and Patterns

### Expression Handling
- Mathematical expressions are stored as strings and evaluated safely using `prepareExpression()` and `safeEval()`
- Expression sanitization happens in `prepareExpression()` which:
  - Normalizes operators (÷ → /, × → *, etc.)
  - Converts percent notation (50% → (50/100))
  - Replaces mathematical functions with Math.* equivalents
  - Validates for unauthorized identifiers

### Mathematical Features
The calculator supports:
- Basic operations: +, -, *, /, %, ()
- Scientific functions: sin, cos, tan (radians)
- Logarithms: log (base 10), ln (natural log)
- Constants: π (pi), e
- Powers: ^ operator
- Other: sqrt, abs

### UI/UX Patterns
- Two-line display showing history and current expression
- Color-coded buttons (operator vs number vs clear)
- Full keyboard support for input
- Error handling with temporary error display

## Development Guidelines
1. All new mathematical functions should be added to `prepareExpression()` with proper Math.* mappings
2. Use the existing CSS variables for consistent styling:
   ```css
   --bg: #0f1724
   --accent: #06b6d4
   --btn: #111827
   --text: #e6eef8
   --danger: #ef4444
   --radius: 12px
   ```
3. Maintain the self-contained nature of the application - no external dependencies

## Security Considerations
- All mathematical expressions are sanitized before evaluation
- The `safeEval()` function uses a restricted Function context
- Input validation prevents execution of arbitrary JavaScript