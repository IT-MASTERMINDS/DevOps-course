
### **1\. Basic Structure of a Jenkins Pipeline**

Jenkins Pipelines can be written as either a **Declarative Pipeline** or a **Scripted Pipeline**. The Declarative Pipeline is simpler and more structured, while the Scripted Pipeline offers more flexibility.

---

### **2\. Declarative Pipeline Syntax**

The Declarative Pipeline is the recommended way to define your pipeline and has a simpler, predefined syntax.

```groovy
pipeline {
    agent any  // Defines where the pipeline will run (e.g., 'any' agent, specific node, or Docker container)

    stages {  // Defines the stages of the pipeline
        stage('Build') {
            steps {
                echo 'Building...'
                // Commands for building your application
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                // Commands for testing your application
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // Commands for deployment
            }
        }
    }
}
```

---

### **3\. Common Pipeline Directives**

* **agent**: Specifies where the pipeline or stage will execute.

  * *Example*: `agent { docker 'maven:3.6.3-jdk-8' }` (to run in a Docker container)

* **stages**: Defines a sequence of one or more stages to execute.

* **steps**: Contains the actions to be performed within a stage.

* **post**: Defines actions to be run after the stages, such as cleanup or notification.

 ```
  post {
      always {
          echo 'This runs always, no matter the build status.'
      }
      success {
          echo 'This runs on successful builds.'
      }
      failure {
          echo 'This runs if the build fails.'
      }
  }
  ```

---

### **4\. Scripted Pipeline Syntax**

A more flexible, but less structured way to define a pipeline.

```groovy
node {
    stage('Build') {
        echo 'Building...'
        // Commands for building
    }
    stage('Test') {
        echo 'Testing...'
        // Commands for testing
    }
    stage('Deploy') {
        echo 'Deploying...'
        // Commands for deployment
    }
}
```

---

### **5\. Common Steps in Jenkins Pipelines**

* **sh**: Executes a shell command.
 ```
  sh 'echo "Running shell command"'
  sh 'mvn clean install'
  ```
* **bat**: Executes a Windows batch command (useful for Windows agents).
 ```
  bat 'dir'
  ```
* **echo**: Prints a message to the console.
 ```
  echo 'Hello, Jenkins!'
  ```
* **checkout**: Checks out code from a version control system (like Git).
 ```
  checkout scm
  ```
* **input**: Pauses the pipeline for human input.
 ```
  input 'Should we proceed with deployment?'
  ```

---

### **6\. Working with Environment Variables**

* **Defining Environment Variables**

 ```
  environment {
      MY_VAR = 'value'
  }
  ```
* **Using Environment Variables**

 ```
  echo "The value of MY_VAR is ${env.MY_VAR}"
  ```

---

### **7\. Running Pipelines in Parallel**

You can run stages in parallel to speed up your builds.

```groovy
stage('Parallel Stage') {
    parallel {
        stage('Unit Tests') {
            steps {
                echo 'Running unit tests...'
                // Unit test commands
            }
        }
        stage('Integration Tests') {
            steps {
                echo 'Running integration tests...'
                // Integration test commands
            }
        }
    }
}
```

---

### **8\. Using `Jenkinsfile`**

* A `Jenkinsfile` is a text file that contains the pipeline code.
* Place the `Jenkinsfile` in the root directory of your project and configure your Jenkins job to use it.

---

### **9\. Example of a Full Jenkinsfile**

Here’s a sample `Jenkinsfile` for a simple build, test, and deploy process:

```groovy
pipeline {
    agent any

    environment {
        APP_ENV = 'production'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                sh 'npm install'
                sh 'npm run build'
            }
        }
        stage('Test') {
            steps {
                sh 'npm test'
            }
        }
        stage('Deploy') {
            steps {
                sh 'npm run deploy'
            }
        }
    }

    post {
        success {
            echo 'Build completed successfully!'
        }
        failure {
            echo 'Build failed. Check the logs for details.'
        }
    }
}
```

These commands and configurations should cover most basic Jenkins Pipeline needs.
