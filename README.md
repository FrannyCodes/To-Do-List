<!DOCTYPE html>
<html>
<head>
    <title>Simple To-Do List</title>
</head>
<body>
    <h1>My To-Do List</h1>
    <input type="text" id="taskInput" placeholder="Add a new task">
    <button onclick="addTask()">Add</button>
    <ul id="taskList">
        <!-- Tasks will be added here -->
    </ul>

    <script>
        function addTask() {
            const taskInput = document.getElementById("taskInput");
            const taskList = document.getElementById("taskList");

            if (taskInput.value !== "") {
                const taskItem = document.createElement("li");
                taskItem.textContent = taskInput.value;

                const deleteButton = document.createElement("button");
                deleteButton.textContent = "Delete";
                deleteButton.onclick = function () {
                    taskList.removeChild(taskItem);
                };

                taskItem.appendChild(deleteButton);
                taskList.appendChild(taskItem);

                taskInput.value = "";
            }
        }
    </script>
</body>
</html>
