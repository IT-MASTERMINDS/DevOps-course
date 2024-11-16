Here are some fundamental Maven commands to help you with building and managing your projects:

---

### **1\. Basic Maven Build Commands**

* **Compile the Project**

 ```
 mvn compile
  ```

  * This command compiles the source code of the project.

* **Clean the Project**

 ```
 mvn clean
  ```

  * Cleans the project by deleting the `target` directory, where compiled code and temporary files are stored.

* **Package the Project**

 ```
 mvn package
  ```

  * Packages the compiled code into a distributable format, like a JAR or WAR file, depending on the project configuration.

* **Install the Package into the Local Repository**

 ```
 mvn install
  ```

  * Installs the package into the local Maven repository (usually located in `~/.m2/repository`), making it available for other projects on your local machine.

* **Run Tests**

 ```
 mvn test
  ```

  * Runs the unit tests defined in the project using frameworks like JUnit.

* **Execute a Full Build (Clean, Compile, Package)**

 ```
 mvn clean package
  ```

  * Cleans the `target` directory and then compiles and packages the project in one go.

---

### **2\. Running and Skipping Tests**

* **Skip Tests During Build**

 ```
 mvn package -DskipTests
  ```

  * Skips running the tests while building the project.
* **Run Only the Tests**

 ```
 mvn test
  ```

  * Executes the tests without compiling or packaging.

---

### **3\. Checking for Dependencies**

* **Download Dependencies**

 ```
 mvn dependency:resolve
  ```

  * Resolves and downloads all dependencies defined in the `pom.xml` file.

* **Display Dependency Tree**

 ```
 mvn dependency:tree
  ```

  * Displays the dependency hierarchy of the project to help identify potential conflicts.

---

### **4\. Running a Project**

* **Run a Maven Project**

 ```
 mvn exec:java -Dexec.mainClass="com.example.MainClass"
  ```

  * Executes the `main` method of the specified class. Replace `"com.example.MainClass"` with the full class name of your main entry point.

---

### **5\. Generate Project Documentation**

* **Generate Project Reports (Site)**

 ```
 mvn site
  ```

  * Generates project documentation, including reports about dependencies, code quality, and test coverage.

---

### **6\. Checking Maven Version**

* **Check the Installed Maven Version**

 ```
 mvn -v
  ```

  * Displays the current Maven version, Java version, and environment information.

---

### **7\. Maven Project Archetype**

* **Create a New Maven Project Using an Archetype**

 ```
 mvn archetype:generate
  ```

  * Helps generate a new Maven project based on an archetype template. The command will guide you through the steps to create a new project.

---

### **8\. Maven Lifecycle Phases**

Maven's build lifecycle consists of a series of phases. Here’s how to use them:

* **Validate**: Validate the project is correct and all necessary information is available.
 ```
 mvn validate
  ```
* **Compile**: Compile the source code.
 ```
 mvn compile
  ```
* **Test**: Run unit tests.
 ```
 mvn test
  ```
* **Package**: Package the compiled code into a JAR/WAR.
 ```
 mvn package
  ```
* **Verify**: Run checks on the package to ensure quality.
 ```
 mvn verify
  ```
* **Install**: Install the package into the local repository.
 ```
 mvn install
  ```
* **Deploy**: Deploy the package to a remote repository for sharing.
 ```
 mvn deploy
  ```

---

These basic Maven commands should cover most of your needs for building, testing, and managing Java projects
