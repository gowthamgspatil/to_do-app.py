# to_do-app.py
This code defines a simple task management applicationin Python. Here's a breakdown of how the code works:
1. Function Definition and Task List Initialization
   - The function task() is defined, and inside it, an empty list tasks is initialized to store the user's tasks.
   - The app begins by printing a welcome message: "----WELCOME TO THE TASK MANAGEMENT APP----".

2. Input for Number of Tasks
   - The user is asked to specify how many tasks they want to add using the input:  
     python:
     total_task = int(input("Enter how many tasks you want to add = "))
     
   - The app then uses a for loop to gather task names from the user based on the number they entered, storing each task in the tasks list:
     python:
     for i in range(1, total_task + 1):
        task_name = input(f"Enter task {i} = ")
        tasks.append(task_name)
     
 3. Displaying Tasks
   - After adding the tasks, the app prints the list of tasks:  
     python:
     print(f"Today's tasks are\n{tasks}")

### 4. **Main Menu for Operations**
   - The app enters a while True loop, which continuously presents a menu to the user for different operations:
     python:
     operation = int(input("Enter \n1-Add\n2-Update\n3-Delete\n4-View\n5-Exit/Stop\n"))

   The user can choose one of the following operations:

   1. Add a Task
   - The user is prompted to enter a new task, which is then appended to the `tasks` list:  
     python:
     add = input("Enter task you want to add = ")
     tasks.append(add)
     print(f"Task '{add}' has been successfully added.")

   2. Update an Existing Task
   - The user is asked to provide the name of the task they want to update. If the task is found in the list, the user is prompted to enter a new value to replace the old task:
    python:
     updated_val = input("Enter the task name you want to update = ")
     if updated_val in tasks:
         up = input("Enter new task = ")
         ind = tasks.index(updated_val)
         tasks[ind] = up
         print(f"Updated task '{updated_val}' to '{up}'.")
     else:
         print("Task not found.")
    

   3. Delete a Task
   - The user is prompted to enter the task they want to delete. If the task is found, it is removed from the list:
    python:
     del_val = input("Which task you want to delete = ")
     if del_val in tasks:
         ind = tasks.index(del_val)
         del tasks[ind]
         print(f"Task '{del_val}' has been deleted.")
     else:
         print("Task not found.")

   4. View All Tasks
   - This option simply prints the current list of tasks:
     python:
     print(f"Total tasks = {tasks}")
     

   5. Exit the Program
   - The program terminates the loop and ends when the user selects the exit option:
     python
     elif operation == 5:
         print("Closing the program....")
         break

   6.Error Handling
   - The app uses a try-except block to catch any invalid input (such as non-integer inputs for the menu choices) and prints an error message without crashing the program:
     python
     except ValueError:
         print("Invalid Input. Please enter a valid number.")

Summary:
- The app allows a user to manage tasks by adding, updating, deleting, and viewing them.
- It operates in a continuous loop until the user chooses to exit by selecting option 5.
- The program includes error handling to prevent crashes due to invalid inputs, and uses lists to store the tasks and make updates dynamically.
