#include <iostream>
#include <string>
using namespace std;


struct Task 
{
    string description;
    bool isCompleted;
};

void showmenu() 
{
    cout << "\n---:TO-DO LIST MANAGER:---" << endl;
    cout << "1. Add Task\n2. View Tasks\n3. Mark Completed\n4. Remove Task\n5. Exit" << endl;
    cout << "Choose an option: ";
}

int main() 
{
    Task tasks[100]; 
    int choice = 0;
    int count = 0;   

    while (true) 
	{
        showmenu();
        cin >> choice;

        if (choice == 5) 
		{
            cout << "Exiting..." << endl;
            break;
        }

        switch (choice) 
		{
            case 1: // Add Task
                if (count < 100) 
				{
                    cout << "Enter your task: ";
                    cin.ignore(); 
                    getline(cin, tasks[count].description);
                    tasks[count].isCompleted = false;
                    count++;
                } 
				else 
				{
                    cout << "List full!" << endl;
                }
                break;

            case 2: // View Tasks
                cout << "\nSr No.\tStatus\t\tTask" << endl;
                for (int i = 0; i < count; i++) 
				{
                    cout << i + 1 << ".\t"<<(tasks[i].isCompleted ? "[Completed]" : "[Pending]  ")<< "\t" << tasks[i].description << endl;
                }
                break;

            case 3: // Mark Completed
                int markid;
                cout << "Enter task no. to mark as completed: ";
                cin >> markid;
                if (markid > 0 && markid <= count) 
				{
                    tasks[markid - 1].isCompleted = true;
                    cout << "Task updated!" << endl;
                } 
				else 
				{
                    cout << "Invalid number!" << endl;
                }
                break;

            case 4: // Remove Task
                int removeid;
                cout << "Enter task no. to remove: ";
                cin >> removeid;
                if (removeid > 0 && removeid <= count) 
				{
                    
                    for (int i = removeid - 1; i < count - 1; i++) 
					{
                        tasks[i] = tasks[i + 1];
                    }
                    count--;
                    cout << "Task removed!" << endl;
                } 
				else 
				{
                    cout << "Invalid number!" << endl;
                }
                break;

            default:
                cout << "INVALID CHOICE" << endl;
        }
    }
    return 0;
}
