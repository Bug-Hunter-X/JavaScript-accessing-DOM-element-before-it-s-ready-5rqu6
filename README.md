# Uncommon HTML/JavaScript Bug: DOM Element Access Timing

This repository demonstrates a subtle bug that can occur when JavaScript code attempts to access and manipulate DOM elements before the browser has fully parsed and rendered the HTML.  This often happens when the JavaScript code is placed within `<head>` or early in `<body>`.

## The Bug
The `bug.html` file contains a simple HTML structure with a `div` element and JavaScript code designed to access the content of this div.  However, the script attempts to access the div before the browser has completely rendered the page, resulting in an error (specifically, a `TypeError` because `document.getElementById('myDiv')` returns null).

## The Solution
The `bugSolution.html` file provides the correct implementation. It uses the `DOMContentLoaded` event listener, ensuring the JavaScript code executes only after the entire HTML document has been parsed and the DOM is ready.

## How to Reproduce
1. Clone this repository.
2. Open `bug.html` in your browser's developer console. You will observe an error.
3. Open `bugSolution.html`. You should see the text from the div correctly logged to the console.

This example highlights the importance of understanding the browser's rendering process and using appropriate techniques to interact with the DOM at the correct time.