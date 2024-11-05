# BasicMathCalculator

A simple web-based calculator that performs basic arithmetic operations. This project includes an HTML structure, CSS styling, and JavaScript functionality to handle button clicks and calculations. It supports addition, subtraction, multiplication, and division.
## Features
Basic Operations: Perform addition, subtraction, multiplication, and division.
Clear Display: The "AC" button clears the display.
Live Updates: Input is updated in real-time as buttons are clicked.
Responsive Design: The calculator layout adapts well on different screen sizes.

## Technologies Used
HTML: Basic structure of the calculator.
CSS: Styling for layout, colors, and hover effects.
JavaScript: Handles button functionality and calculations.
## Setup and Usage
1. *Clone or download* the repository.
2. *Open the HTML file* in any modern web browser to run the calculator.

## Code Explanation
The code consists of the following parts:

### HTML Structure
 <div id="display">: Displays the current input or result.
<div id="keys">`: Contains the calculator buttons arranged in a grid layout.

### CSS Styling
*#calculator*: Central container for the calculator with styling for box-shadow, padding, and border-radius.
*#display*: Styled to show the input/result text aligned to the right.
*#keys > div*: Styles each button with a shadow, font size, and color. Includes hover effects for interaction feedback.

### JavaScript Functionality
JavaScript handles the calculator's functionality:
1. *Event Listeners*: Each button has an event listener that calls the `myCalculator` function on click.
2. *`myCalculator` function*: Manages different button actions:
   *AC*: Clears the display.
   *=*: Evaluates the current expression using `eval()`.
   Numbers and Operators**: Appends clicked buttons to the display and updates the input string.

```javascript
let key = document.querySelectorAll("#keys>div");
let bag = "";
for (let i = 0; i < key.length; i++) {
    key[i].addEventListener("click", myCalculator)
}
function myCalculator(event) {
    let targetNumber = event.target.innerText;
    if (targetNumber == "AC") {
        bag = "";
        document.querySelector("#display").innerText = bag;
    }
    else if (targetNumber == "=") {
        document.querySelector("#display").innerText = eval(bag);
    }
    else {
        bag += targetNumber;
        document.querySelector("#display").innerText = bag;
    }
}
