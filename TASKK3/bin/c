import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

class Task {
    private int id;
    private String name;
    private String description;

    // Constructor
    public Task(int id, String name, String description) {
        this.id = id;
        this.name = name;
        this.description = description;
    }

    // Getters and Setters
    public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getDescription() {
        return description;
    }

    public void setDescription(String description) {
        this.description = description;
    }

    @Override
    public String toString() {
        return "Task [id=" + id + ", name=" + name + ", description=" + description + "]";
    }
}

public class TaskManager {
    private List<Task> tasks = new ArrayList<>();
    private int nextId = 1; // To assign unique IDs to tasks
    private Scanner scanner = new Scanner(System.in);

    // Create a new task
    public void createTask() {
        System.out.println("Enter task name:");
        String name = scanner.nextLine();
        System.out.println("Enter task description:");
        String description = scanner.nextLine();

        Task task = new Task(nextId++, name, description);
        tasks.add(task);
        System.out.println("Task created successfully!");
    }

    // Read and display tasks
    public void readTasks() {
        if (tasks.isEmpty()) {
            System.out.println("No tasks available.");
        } else {
            System.out.println("Task List:");
            for (Task task : tasks) {
                System.out.println(task);
            }
        }
    }

    // Update task details
    public void updateTask() {
        System.out.println("Enter task ID to update:");
        int id = Integer.parseInt(scanner.nextLine());
        Task task = findTaskById(id);

        if (task != null) {
            System.out.println("Enter new task name:");
            String name = scanner.nextLine();
            System.out.println("Enter new task description:");
            String description = scanner.nextLine();

            task.setName(name);
            task.setDescription(description);
            System.out.println("Task updated successfully!");
        } else {
            System.out.println("Task not found.");
        }
    }

    // Delete a task
    public void deleteTask() {
        System.out.println("Enter task ID to delete:");
        int id = Integer.parseInt(scanner.nextLine());
        Task task = findTaskById(id);

        if (task != null) {
            tasks.remove(task);
            System.out.println("Task deleted successfully!");
        } else {
            System.out.println("Task not found.");
        }
    }

    // Helper method to find a task by ID
    private Task findTaskById(int id) {
        for (Task task : tasks) {
            if (task.getId() == id) {
                return task;
            }
        }
        return null;
    }

    // Main menu
    public void showMenu() {
        while (true) {
            System.out.println("\nTask Manager");
            System.out.println("1. Create Task");
            System.out.println("2. Read Tasks");
            System.out.println("3. Update Task");
            System.out.println("4. Delete Task");
            System.out.println("5. Exit");
            System.out.print("Choose an option: ");

            int choice = Integer.parseInt(scanner.nextLine());

            switch (choice) {
                case 1:
                    createTask();
                    break;
                case 2:
                    readTasks();
                    break;
                case 3:
                    updateTask();
                    break;
                case 4:
                    deleteTask();
                    break;
                case 5:
                    System.out.println("Exiting...");
                    return;
                default:
                    System.out.println("Invalid choice. Please try again.");
            }
        }
    }

    public static void main(String[] args) {
        TaskManager taskManager = new TaskManager();
        taskManager.showMenu();
    }
}
