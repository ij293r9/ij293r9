// Define a Task class to represent individual tasks
class Task {
  constructor(title, description, priority) {
    this.title = title;
    this.description = description;
    this.priority = priority;
    this.completed = false;
  }

  markAsCompleted() {
    this.completed = true;
  }
}

// Define a TaskManager class to manage tasks
class TaskManager {
  constructor() {
    this.tasks = [];
  }

  addTask(title, description, priority) {
    const task = new Task(title, description, priority);
    this.tasks.push(task);
  }

  getTasks() {
    return this.tasks;
  }

  getTasksByPriority(priority) {
    return this.tasks.filter(task => task.priority === priority);
  }

  markTaskAsCompleted(taskIndex) {
    if (taskIndex >= 0 && taskIndex < this.tasks.length) {
      this.tasks[taskIndex].markAsCompleted();
    }
  }
}

// Usage example:
const taskManager = new TaskManager();

// Add tasks
taskManager.addTask("Implement login feature", "Create a login form and authentication logic", "High");
taskManager.addTask("Refactor code", "Improve code readability and maintainability", "Medium");
taskManager.addTask("Write documentation", "Prepare user guides and API documentation", "Low");

// Get all tasks
const allTasks = taskManager.getTasks();
console.log("All tasks:", allTasks);

// Get tasks with high priority
const highPriorityTasks = taskManager.getTasksByPriority("High");
console.log("High priority tasks:", highPriorityTasks);

// Mark the first task as completed
taskManager.markTaskAsCompleted(0);

// Get updated list of tasks
const updatedTasks = taskManager.getTasks();
console.log("Updated tasks:", updatedTasks);
