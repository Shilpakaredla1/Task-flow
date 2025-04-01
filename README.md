# Task-flow
mport { useState } from "react";

export default function TaskFlow() {
  const [tasks, setTasks] = useState([
    { id: 1, text: "Set up GitHub repo", completed: true },
    { id: 2, text: "Create Next.js project", completed: false },
    { id: 3, text: "Push project to GitHub", completed: false },
  ]);

  const toggleTask = (id) => {
    setTasks(
      tasks.map((task) =>
        task.id === id ? { ...task, completed: !task.completed } : task
      )
    );
  };

  return (
    <div className="min-h-screen flex items-center justify-center bg-gray-100 p-4">
      <div className="bg-white p-6 rounded-lg shadow-md w-full max-w-md">
        <h1 className="text-xl font-bold mb-4">Task Flow - Task Manager</h1>
        <ul>
          {tasks.map((task) => (
            <li
              key={task.id}
              className={`p-2 border-b flex justify-between items-center ${
                task.completed ? "line-through text-gray-500" : ""
              }`}
            >
              {task.text}
              <button
                onClick={() => toggleTask(task.id)}
                className="bg-blue-500 text-white px-2 py-1 rounded"
              >
                {task.completed ? "Undo" : "Complete"}
              </button>
            </li>
          ))}
        </ul>
      </div>
    </div>
  );
}
git add README.md
git commit -m "Added README"
git push origin main
