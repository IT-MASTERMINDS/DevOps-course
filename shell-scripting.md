
### 1\. **Starting a Script with Shebang**

* Every shell script should start with a shebang (`#!`) to specify the interpreter:
 ```
 #!/bin/bash
  ```

### 2\. **Echo Command**

* Used to print text to the terminal.
 ```
 echo "Hello, World!"
  ```

### 3\. **Variables**

* Define and use variables:
 ```
 NAME="Slav"
 echo "My name is $NAME"
  ```

### 4\. **Reading User Input**

* Use `read` to get input from the user.
 ```
 echo "Enter your name:"
 read NAME
 echo "Hello, $NAME!"
  ```

### 5\. **Conditional Statements**

* **If-Else Example**:
 ```
 #!/bin/bash
  echo "Enter a number:"
  read NUMBER
  if [ $NUMBER -gt 10 ]; then
    echo "The number is greater than 10"
  else
    echo "The number is 10 or less"
  fi
  ```

### 6\. **Loops**

* **For Loop**:
 ```
 for i in {1..5}; do
    echo "Number $i"
  done
  ```
* **While Loop**:
 ```
 COUNT=1
  while [ $COUNT -le 5 ]; do
    echo "Count: $COUNT"
    ((COUNT++))
  done
  ```

### 7\. **Functions**

* Define and call functions within a script.
 ```
 my_function() {
    echo "This is a function"
  }
  my_function  # Call the function
  ```

### 8\. **Command Substitution**

* Capture the output of a command and store it in a variable.
  
 ```
 DATE=$(date)
 echo "Today's date is $DATE"
  ```

### 9\. **Working with Arguments**

* Access arguments passed to the script using `$1`, `$2`, etc.
 ```
 #!/bin/bash
  echo "First argument: $1"
  echo "Second argument: $2"
  ```
* Run the script as: `./script.sh arg1 arg2`

### 10\. **Basic File Operations**

* **Creating a File**:
 ```
 touch myfile.txt
  ```
* **Writing to a File**:
 ```
 echo "Some text" > myfile.txt  # Overwrites the file
  echo "More text" >> myfile.txt # Appends to the file
  ```
* **Reading a File**:
 ```
 while IFS= read -r line; do
    echo "$line"
  done < myfile.txt
  ```

### 11\. **Using `chmod` to Make Script Executable**

* Grant execute permissions to your script:
 ```
 chmod +x script.sh
  ```

### 12\. **Exit Codes**

* Use `exit` to exit the script with a status code.
 ```
 if [ -z "$NAME" ]; then
    echo "Name not provided"
    exit 1
  fi
  ```

### 13\. **Simple Script Example**

* Here is a basic script that combines several concepts:
 ```
 #!/bin/bash
  echo "Enter a directory name:"
  read DIR

  if [ -d "$DIR" ]; then
    echo "Directory $DIR exists"
  else
    echo "Directory $DIR does not exist. Creating now..."
    mkdir "$DIR"
    echo "Directory $DIR created"
  fi
  ```
