
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>To-Do List</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f0f4f8;
      display: flex;
      justify-content: center;
      align-items: flex-start;
      height: 100vh;
      padding-top: 50px;
      margin: 0;
    }

    .todo-container {
      background: #fff;
      padding: 20px 30px;
      border-radius: 10px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.1);
      width: 300px;
    }

    h2 {
      text-align: center;
      margin-bottom: 20px;
    }

    input[type="text"] {
      width: 100%;
      padding: 10px;
      margin-bottom: 15px;
      border: 1px solid #ccc;
      border-radius: 5px;
    }

    button {
      width: 100%;
      padding: 10px;
      background-color: #28a745;
      border: none;
      color: white;
      font-size: 16px;
      border-radius: 5px;
      cursor: pointer;
    }

    button:hover {
      background-color: #218838;
    }

    ul {
      list-style: none;
      padding: 0;
    }

    li {
      background: #f8f9fa;
      padding: 10px;
      margin-bottom: 8px;
      border-radius: 5px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .remove {
      color: red;
      cursor: pointer;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <div class="todo-container">
    <h2>My To-Do List</h2>
    <input type="text" id="taskInput" placeholder="Add a new task...">
    <button onclick="addTask()">Add Task</button>
    <ul id="taskList"></ul>
  </div>

  <script>
    function addTask() {
      const input = document.getElementById("taskInput");
      const task = input.value.trim();
      if (task === "") return;

      const li = document.createElement("li");
      li.innerHTML = `${task} <span class="remove" onclick="this.parentElement.remove()">×</span>`;
      document.getElementById("taskList").appendChild(li);
      input.value = "";
    }
  </script>
</body>
</html>
