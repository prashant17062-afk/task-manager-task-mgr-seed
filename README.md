Academic Task Manager - README

Summary
This Academic Task Manager is a client-side web application designed to help users track their academic tasks. It provides a simple, intuitive interface for managing a list of tasks, marking them as complete or incomplete, and viewing overall progress. Task states are persistently stored in the browser's local storage, ensuring continuity across sessions. The application aims for clarity and ease of use, making it an ideal tool for students and academics.

Setup
This application is entirely contained within a single `index.html` file, making its setup straightforward and requiring no complex environment configurations.

To get started:
1. Save the provided HTML code into a file named `index.html` on your local computer.
2. Open this `index.html` file using any modern web browser (e.g., Google Chrome, Mozilla Firefox, Microsoft Edge, Apple Safari). The application will load directly in your browser.

Usage
Once the `index.html` file is opened in your browser:
- You will see a list of predefined academic tasks.
- Each task is presented as a list item with a checkbox next to it.
- To mark a task as completed, simply click on its associated checkbox. The task's text will display a strikethrough, and the "Completed" count at the top of the page will increment.
- To revert a task to an incomplete state, click the checkbox again. The strikethrough will be removed, and the "Completed" count will decrement.
- The completion status of all your tasks is automatically saved to your browser's local storage. This ensures that your task progress is retained even if you close and reopen your browser or refresh the page.

Main Code Logic
The core functionality of the Academic Task Manager is implemented using JavaScript embedded directly within the `index.html` file.

1.  Initial Task Loading: The application starts by defining an `initialTasks` array, which serves as a default list of tasks. The `loadTasks()` function is responsible for checking the browser's `localStorage` for a key named `userTasks`. If data exists, it's parsed and used; otherwise, the `initialTasks` are loaded and then immediately saved to `localStorage` for future sessions.

2.  Persistent Data Storage: The `saveTasks()` function serializes the current state of the `tasks` array (which holds all task objects) into a JSON string and stores it in `localStorage`. This ensures that any changes made by the user are saved and restored upon subsequent visits.

3.  Dynamic UI Rendering: The `renderTasks()` function dynamically populates the `#task-list` unordered list. For each task in the `tasks` array, it creates a new Bootstrap-styled list item (`<li>`) that contains an `<input type="checkbox">` and a `<label>`. The checkbox's `checked` attribute reflects the task's `completed` status, and an event listener is attached to handle user interaction.

4.  Task State Management: An event listener is added to each task's checkbox. When a checkbox's state changes, it triggers the `toggleTaskCompletion(id)` function. This function locates the specific task using its unique `id`, toggles its `completed` boolean property, and then calls `saveTasks()` to persist the change and `updateCounts()` to reflect the new summary.

5.  Progress Tracking: The `updateCounts()` function calculates the number of tasks currently marked as complete by filtering the `tasks` array. It then updates the `textContent` of the `#completed-count` and `#total-count` HTML elements, providing a real-time summary of the user's progress.

6.  Bootstrap Integration: The application utilizes Bootstrap 5 for its responsive layout and consistent UI components, such as list groups and form checks, enhancing the overall user experience. Custom CSS is also included to fine-tune the visual appearance.

License
This project is released under the MIT License. A copy of the license information is included in the footer of the `index.html` file.

Contact
For any inquiries, suggestions, or issues, please feel free to contact:
[Your Name/Alias]
[Your Email Address, e.g., student.contact@example.com]