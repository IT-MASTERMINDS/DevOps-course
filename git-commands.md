Here are some fundamental Git commands that you’ll frequently use for version control:

---

### **1\. Configuration Commands**

* **Set User Name**

 ```
 git config --global user.name "Your Name"
  ```
* **Set Email Address**

 ```
 git config --global user.email "you@example.com"
  ```
* **View Configurations**

 ```
 git config --list
  ```

---

### **2\. Creating and Cloning Repositories**

* **Initialize a New Git Repository**

 ```
 git init
  ```

  * This creates a new Git repository in your current directory.
* **Clone an Existing Repository**

 ```
 git clone <repository_url>
  ```

  * *Example*: `git clone https://github.com/user/repo.git`

---

### **3\. Basic File Operations**

* **Check the Status of Your Working Directory**

 ```
 git status
  ```

* **Add Changes to Staging Area**

  * Add a specific file:
   ```
   git add <file_name>
    ```
  * Add all changes:
   ```
   git add .
    ```

* **Commit Changes with a Message**

 ```
 git commit -m "Your commit message"
  ```

* **Remove a File and Stage the Deletion**

 ```
 git rm <file_name>
  ```

* **Move or Rename a File**

 ```
 git mv <old_file_name> <new_file_name>
  ```

---

### **4\. Viewing History and Differences**

* **View Commit History**

 ```
 git log
  ```

  * Use `git log --oneline` for a more condensed view.
* **View Changes in Your Working Directory**

 ```
 git diff
  ```
* **View Changes Between Staged and Last Commit**

 ```
 git diff --staged
  ```

---

### **5\. Branching and Merging**

* **List All Branches**

 ```
 git branch
  ```
* **Create a New Branch**

 ```
 git branch <branch_name>
  ```
* **Switch to a Branch**

 ```
 git checkout <branch_name>
  ```
* **Create and Switch to a New Branch**

 ```
 git checkout -b <branch_name>
  ```
* **Merge a Branch into the Current Branch**

 ```
 git merge <branch_name>
  ```
* **Delete a Branch**

 ```
 git branch -d <branch_name>
  ```

---

### **6\. Remote Repositories**

* **Add a Remote Repository**

 ```
 git remote add <remote_name> <repository_url>
  ```

  * *Example*: `git remote add origin https://github.com/user/repo.git`
* **View Remote Repositories**

 ```
 git remote -v
  ```
* **Fetch Changes from Remote**

 ```
 git fetch <remote_name>
  ```
* **Push Changes to Remote Repository**

 ```
 git push <remote_name> <branch_name>
  ```

  * *Example*: `git push origin main`
* **Pull Changes from Remote Repository**

 ```
 git pull <remote_name> <branch_name>
  ```

  * *Example*: `git pull origin main`

---

### **7\. Stashing Changes**

* **Stash Uncommitted Changes**

 ```
 git stash
  ```
* **View Stashed Changes**

 ```
 git stash list
  ```
* **Apply Stashed Changes**

 ```
 git stash apply
  ```
* **Drop the Stash**

 ```
 git stash drop
  ```

---

### **8\. Undoing Changes**

* **Unstage Changes**

 ```
 git reset <file_name>
  ```
* **Undo Changes in Working Directory**

 ```
 git checkout -- <file_name>
  ```
* **Reset to a Previous Commit (Destructive)**

 ```
 git reset --hard <commit_id>
  ```

These commands are essential for everyday Git operations, whether you are collaborating on projects or maintaining a codebase.
