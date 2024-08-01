
## Technology used. 
HTML, CSS, Javascript

# JavaScript Logic Explanation
Below is an explanation of how the JavaScript code is structured and functions. The line numbers correspond to those in your JavaScript file. 

# Note:
## Line Number:  
The numbers in the notes correspond to the lines in your JavaScript file. Some lines are out of order to match the logical flow of the application.



# Creating Constant Variables:

1. ## `inputBox`
A constant variable that gets the value from the element with the ID `input-box`

2. ## `listContainer`
 A constant variable that gets the value from the element with the ID `list-container`

# Function Definitions:

4. ## Define Function `addTask()`:
 This function is responsible for adding tasks to the list
 
6. ## Check for Empty input-box 
This if statement check for the empty input-box.

7. ### If Empty
If inputBox is empty, display an alert: `You must write something!`.

9. ### Not Empty
If inputBox is not empty, proceed with the following steps:

10. ## Create `li` element
 Declare a variable `li` to create an `li` element using `document.createElement("li")`.
 
11. ## Set `li` Inner HTML:
 Assign the value of inputBox to `li.innerHTML`, which writes the input value inside the `li` element.
 
12. ## Append `li` to `listContainer`
Use `listContainer.appendChild(li)` to add the newly created `li` element to the `listContainer`.

17. ## Clear `inputBox`
After adding the task, set `inputBox.value` to an empty string to clear the input field.

13. ## Create `span` Element:
Declare a variable `span` and create a span element using `document.createElement("span")`.

14. ## Set `span` Content:
Assign the Unicode character `\u00d7` to `span.innerHTML` for displaying a delete symbol.

15. ## Display `span`
Append the `span` element to the `li`, making it visible in the list.

# Event Handling

21. ## Add Click Event Listner:
Add an event listener to `listContainer` to listen for click events. The function `(e)` determines which element is clicked.

23. ## Check Clicked Elemet `LI`:
 If the clicked element is an `LI` tag:
 
24. ## Toggle Checked Class:
Use `e.target.classList.toggle("checked")` to add or remove the `checked` class, which applies a line-through style via CSS.

27. ## Check Clicked Element `span`
If the clicked element is a `SPAN` tag:

28. ## Remove Parent `li`:
Remove the parent `li` element, effectively deleting the task.

31. ## Event Propagation `false`:
The third parameter `false` in `addEventListener` indicates that the event listener is in the bubbling phase. This means the event propagates from the inside out (e.g., from `SPAN` to `LI`).

# Data Persistence

33. ## Function `saveData()`:
Store the entire content of `listContainer` in `localStorage` with the key `data`. This ensures that the list can be retrieved and restored.

34. ## Data Storage:
Save the HTML content of listContainer to `localStorage`, which allows retrieval and display of the list upon page refresh.

18. ### Call `saveData():
After adding the task, call `saveData()` to store the updated list in localStorage.

25 .### Call `saveData()`:
Save the updated state to `localStorage` since the class `checked` may be added.

29. ### Call `saveData()`:
Save the updated list to `localStorage` since the task was removed.

# Displaying Stored Data

37. ## Function `showTask()`:
Define a function to display tasks from `localStorage` when the page loads.

38. ## Retrieve and Display Data:
On page load or refresh, set `listContainer.innerHTML` to the content retrieved from `localStorage` using the key `data`.

41. ## Call `showTask()`:
Immediately call `showTask()` to display the saved tasks when the page loads.




