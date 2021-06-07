
pipeline {
    agent any
    environment{
      AUTHOR='amalonga'
     // SERVER_CREDENTIALS = credentials('add-ssh-users')
      
    }
    stages {
        stage('Hello') {
            when{
           	expression{
                   BRANCH_NAME == 'dev-add-users-via-jenkins-job' 
                }

            }
            steps {
                echo 'Hello World'
               // echo ' this done by M. $AUTHOR'
            }
        }
    }
}

