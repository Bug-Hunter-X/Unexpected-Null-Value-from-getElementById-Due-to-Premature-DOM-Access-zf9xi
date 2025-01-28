# Uncommon HTML Error: Premature DOM Access

This repository demonstrates a subtle error related to accessing HTML DOM elements before they are fully loaded into the Document Object Model (DOM). The error arises when trying to use `getElementById` on an element that hasn't been parsed and added to the DOM yet.

## Bug Description:

The `bug.html` file attempts to access a div element using `getElementById` within a `<script>` tag placed before the element's declaration in the HTML structure. This causes `document.getElementById('myDiv')` to return `null` because the element doesn't exist yet in the DOM.

## Solution:

The `bugSolution.html` file shows the corrected approach. The script is moved to the end of the `<body>` just before the closing `</body>` tag, ensuring that the script executes after the elements have been fully loaded into the DOM. Alternatively, you can use `addEventListener('DOMContentLoaded', function(){...})` to ensure the DOM is ready before executing the script.

## How to Reproduce:

1. Open `bug.html` in a web browser.
2. Observe the error in the browser's console.
3. Open `bugSolution.html` to see the corrected version.
