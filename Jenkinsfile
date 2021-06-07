
pipeline {
    agent any
    environment{
     def AUTHOR='amalonga'
     // SERVER_CREDENTIALS = credentials('add-ssh-users')
      
    }
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
                echo ' this done by M. ${AUTHOR} '
            }
        }
    }
}

