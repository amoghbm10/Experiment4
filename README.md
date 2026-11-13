EXPERIMENT 1

git --version
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
git config --global --list
mkdir Gitlab
cd Gitlab
git init
ls -a
git status
touch program1.txt
git status
nano program1.txt
git status
git add program1.txt
git status
git commit -m "VERSION 1"
git log
git log --oneline
git show HEAD
nano program1.txt
git status
git diff
git add program1.txt
git commit -m "VERSION 2"
nano program1.txt
git commit -am "Update semester"


EXPERIMENT 2

cd Gitlab
git log --oneline
git branch
git branch feature-branch
git branch
git checkout feature-branch
git branch
ls
nano file1.txt
git status
git add file1.txt
git status
git commit -m "This file is created in feature-branch"
git log --oneline
git checkout master
git branch
git log --oneline
ls
git merge feature-branch
git status
ls
git log --oneline
git log --oneline --graph --all
git branch
git branch -v
git branch --merged
git branch -d feature-branch
git branch


EXPERIMENT 3

cd Gitlab
git log --oneline
git branch
git checkout feature-branch
git branch
ls
nano student.txt
git status
git stash save "My temporary changes on student.txt"
git status
git stash list
git checkout master
git branch
ls
git stash list
git add .
git stash apply
git status
ls
cat student.txt
git stash list
git stash drop
git stash list
git stash clear


EXPERIMENT 4

cd Desktop
mkdir Experiment4
cd Experiment4
git clone https://github.com/YourUsername/Experiment4.git
ls
cd Experiment4
git status
git remote -v
ls
cat README.md


EXPERIMENT 5

cd Desktop
cd Experiment4
cd Experiment4
pwd
ls -a
git branch
git status
git remote -v
git switch main
git pull origin main
notepad local-notes.txt
git add local-notes.txt
git commit -m "Add local notes for Experiment 5"
git log --oneline
git fetch origin
git status
git branch
git rebase origin/main
git log --oneline
git push origin main


EXPERIMENT 6

cd Desktop
cd Experiment4
cd Experiment4
pwd
ls -a
git status
git branch
git remote -v
git pull origin main
git branch feature-branch
git switch feature-branch
notepad book-search.txt
git add book-search.txt
git commit -m "Add book search feature"
git log --oneline
git switch main
git branch
git merge --no-ff feature-branch -m "Merge book search feature"
git status
git show HEAD
git branch --merged
git push origin main




#include <stdio.h> 
#include <stdlib.h> 
// Structure for employee 
struct Employee { 
 char ssn[20];
 char name[50];
 char dept[30];
 char designation[30];
 float salary;
 char phone[15];
 struct Employee* prev;
 struct Employee* next;
};
// Create a new employee node 
struct Employee* createEmployee() 
{ 
 struct Employee* newEmployee;
 newEmployee = (struct Employee*)malloc(sizeof(struct Employee));
 if (newEmployee == NULL) { 
 printf("Memory allocation failed!\n");
 exit(1);
 } printf("Enter SSN: ");
 scanf("%25s", newEmployee->ssn);
 printf("Enter Name: ");
 scanf(" %25[^\n]", newEmployee->name);
 printf("Enter Department: ");
 scanf(" %25[^\n]", newEmployee->dept);
 printf("Enter Designation: ");
 scanf(" %25[^\n]", newEmployee->designation);
 printf("Enter Salary: ");
 scanf("%f", &newEmployee->salary);
 printf("Enter Phone Number: ");
 scanf("%14s", newEmployee->phone);
 newEmployee->prev = NULL;
 newEmployee->next = NULL;
 return newEmployee;
} 
// Insert employee at front 
struct Employee* insertFront(struct Employee* head) 
{ 
 struct Employee* newEmployee = createEmployee();
 if (head == NULL) { 
 head = newEmployee;
 } 
 else { 
 newEmployee->next = head;
 head->prev = newEmployee;
 head = newEmployee;
 } 
 printf("Employee inserted at front successfully.\n");
 return head;
} // Insert employee at end 
struct Employee* insertEnd(struct Employee* head) 
{ 
 struct Employee* newEmployee = createEmployee();
 if (head == NULL) { 
 head = newEmployee;
 } 
 else { 
 struct Employee* temp = head;
 while (temp->next != NULL) { 
 temp = temp->next;
 } 
 temp->next = newEmployee;
 newEmployee->prev = temp;
 } 
 printf("Employee inserted at end successfully.\n");
 return head;
} 
// Delete employee from front 
struct Employee* deleteFront(struct Employee* head) 
{ 
 if (head == NULL) { 
 printf("List is empty. Nothing to delete.\n");
 } 
 else { 
 struct Employee* temp = head;
 printf("Deleted employee: %s\n", temp->name);
 head = head->next;
 if (head != NULL) { 
 head->prev = NULL;
 } 
 free(temp); } 
 return head;
} 
// Delete employee from end 
struct Employee* deleteEnd(struct Employee* head) 
{ 
 if (head == NULL) { 
 printf("List is empty. Nothing to delete.\n");
 } 
 else if (head->next == NULL) { 
 printf("Deleted employee: %s\n", head->name);
 free(head);
 head = NULL;
 } 
 else { 
 struct Employee* temp = head;
 while (temp->next != NULL) { 
 temp = temp->next;
 } 
 printf("Deleted employee: %s\n", temp->name);
 temp->prev->next = NULL;
 free(temp);
 } 
 return head;
} 
// Display all employees and count nodes 
void display(struct Employee* head) 
{ 
 struct Employee* temp = head;
 int count = 0;
 if (head == NULL) { 
 printf("Employee database is empty.\n");
 printf("Total number of employees: 0\n"); return;
 } 
 printf("\n------ Employee Records ------\n");
 while (temp != NULL) { 
 printf("\nSSN: %s", temp->ssn);
 printf("\nName: %s", temp->name);
 printf("\nDepartment: %s", temp->dept);
 printf("\nDesignation: %s", temp->designation);
 printf("\nSalary: %.2f", temp->salary);
 printf("\nPhone Number: %s\n", temp->phone);
 count++;
 temp = temp->next;
 } 
 printf("\n------------------------------\n");
 printf("Total number of employees: %d\n", count);
} 
// Main function 
int main() 
{ 
 struct Employee* head = NULL;
 int choice, n, i;
 do { 
 printf("\n===== EMPLOYEE DATABASE USING DLL =====\n");
 printf("1. Create DLL of N Employees\n");
 printf("2. Display Employees and Count Nodes\n");
 printf("3. Insert Employee at End\n");
 printf("4. Delete Employee from End\n");
 printf("5. Insert Employee at Front\n");
 printf("6. Delete Employee from Front\n");
 printf("7. Exit\n");
 printf("Enter your choice: ");
 scanf("%d", &choice);
 switch (choice) { case 1: 
 printf("Enter number of employees: ");
 scanf("%d", &n);
 if (n <= 0) { 
 printf("Enter a valid number of employees.\n");
 break;
 } 
 for (i = 0; i < n; i++) {
 printf("\nEnter details of employee %d:\n", i + 1);
 head = insertEnd(head);
 } 
 break;
 case 2: 
 display(head);
 break;
 case 3: 
 head = insertEnd(head);
 break;
 case 4: 
 head = deleteEnd(head);
 break;
 case 5: 
 head = insertFront(head);
 break;
 case 6: 
 head = deleteFront(head);
 break;
 case 7: 
 printf("Exiting Employee Database...\n");
 break;
 default: 
 printf("Invalid choice. Try again.\n");
 } } while (choice != 7);
 // Free all remaining nodes
 while (head != NULL) {
 struct Employee* temp = head;
 head = head->next;
 free(temp);
 }
 return 0;
}
