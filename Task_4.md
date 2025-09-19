<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>To-Do List App</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f6f8;
      text-align: center;
      margin: 0;
      padding: 20px;
    }

    h1 {
      color: #333;
    }

    .todo-container {
      max-width: 400px;
      margin: auto;
      background: white;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0px 4px 10px rgba(0,0,0,0.1);
    }

    input[type="text"] {
      padding: 10px;
      width: 70%;
      border: 1px solid #ccc;
      border-radius: 5px;
      outline: none;
    }

    button {
      padding: 10px 15px;
      margin-left: 5px;
      background: #0077b6;
      border: none;
      border-radius: 5px;
      color: white;
      cursor: pointer;
    }

    button:hover {
      background: #023e8a;
    }

    ul {
      list-style-type: none;
      padding: 0;
      margin-top: 20px;
    }

    li {
      background: #e9ecef;
      padding: 10px;
      margin: 5px 0;
      border-radius: 5px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .delete-btn {
      background: red;
      color: white;
      border: none;
      border-radius: 5px;
      padding: 5px 10px;
      cursor: pointer;
    }

    .delete-btn:hover {
      background: darkred;
    }
  </style>
</head>
<body>
  <h1>To-Do List</h1>
  <div class="todo-container">
    <input type="text" id="taskInput" placeholder="Enter a new task">
    <button onclick="addTask()">Add</button>
    <ul id="taskList"></ul>
  </div>

  <script>
    function addTask() {
      const input = document.getElementById("taskInput");
      const taskText = input.value.trim();

      if (taskText === "") {
        alert("Please enter a task!");
        return;
      }

      const li = document.createElement("li");
      li.textContent = taskText;

      // Create delete button
      const deleteBtn = document.createElement("button");
      deleteBtn.textContent = "Delete";
      deleteBtn.classList.add("delete-btn");
      deleteBtn.onclick = function () {
        li.remove();
      };

      li.appendChild(deleteBtn);
      document.getElementById("taskList").appendChild(li);

      input.value = ""; // clear input
    }
  </script>
</body>
</html>
