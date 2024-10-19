
# To-Do List Program

# Initialize an empty list to store tasks
tasks = []

# Function to add a new task
def add_task():
    task = input("Enter a new task: ")
    tasks.append({"task": task, "status": "pending"})
    print("Task added!")

# Function to update a task
def update_task():
    task_number = int(input("Enter the task number to update: ")) - 1
    if task_number < len(tasks):
        task = tasks[task_number]
        print("Current task:", task["task"])
        print("Current status:", task["status"])
        new_status = input("Enter new status (pending/done): ")
        task["status"] = new_status
        print("Task updated!")
    else:
        print("Invalid task number.")

# Function to display all tasks
def display_tasks():
    for i, task in enumerate(tasks, start=1):
        print(f"{i}. {task['task']} - {task['status']}")

# Main program loop
while True:
    print("\nTo-Do List Program")
    print("1. Add task")
    print("2. Update task")
    print("3. Display tasks")
    print("4. Exit")
    choice = input("Enter your choice: ")

    if choice == "1":
        add_task()
    elif choice == "2":
        update_task()
    elif choice == "3":
        display_tasks()
    elif choice == "4":
        break
    else:
        print("Invalid choice. Please try again.")
