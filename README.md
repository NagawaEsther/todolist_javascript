Data Storage:
I used an array called todos to store todo items. Each item is an object with two properties:


text: The actual text content of the todo item.


done: A boolean flag indicating whether the todo is completed (true) or not (false).


Adding Todos:


The addTodo() function handles adding new todos.


It retrieves the value from the input field with the ID todoInput.


It trims any leading or trailing whitespace from the input using trim().


If the input isn't empty:


It creates a new todo object with the trimmed text and sets done to false.


It pushes this object onto the todos array.


It calls displayTodos() to update the UI with the new list.


Finally, it clears the input field for the next entry.


Displaying Todos:


The displayTodos() function is responsible for showing the list of todos on the page.


It first clears any existing content from the element with the ID todoList.


Then, it iterates over each todo item in the todos array using forEach().


Inside the loop, it creates a new <li> element for each todo item and sets its class to todo-item.


It dynamically builds the HTML content for the list item using template literals (backticks). This content includes:


A checkbox for marking the todo as done. The onchange event calls toggleDone() with the current item's index. The checkbox is checked based on the done property value.


A <span> element to display the todo text. It also has a class (done for completed items) based on the done property.


A container (div) with two buttons:


"Edit" button calls editTodo() with the index.


"Delete" button calls deleteTodo() with the index.


Finally, it appends the created list item (<li>) to the todoList element.


Note: The todo items are dynamically generated based on the content of the todos array.


Managing Todos:


The deleteTodo() function removes a todo item from the list.


It takes the index of the item to be deleted as an argument.


It uses the splice() method on the todos array to remove the element at that specific index.


After deletion, it calls displayTodos() to update the UI with the modified list.


The editTodo() function allows editing the text of an existing todo item.


It prompts the user for new text using prompt().


If the user enters a value and it's not empty after trimming, it updates the text property of the todo object at the given index with the new text.


Similar to other functions, it calls displayTodos() to reflect the changes in the UI.


The toggleDone() function toggles the completion status of a todo item.


It takes the index of the item as an argument.


It uses a logical NOT operator (!) to flip the value of the done property for the todo at that index.


Again, it calls displayTodos() to update the UI with the change in completion status.


Initial Render:


The line displayTodos(); outside any function calls this function on page load. This ensures the existing todos (if any) are displayed when the application starts.


