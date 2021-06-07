
//CODE_CHANGES = getGitChanges()
CODE_CHANGES = true
pipeline {
    agent any
    environment{
      AUTHOR='amalonga'
      SERVER_CREDENTIALS = credentials('add-ssh-users')
      
    }
    stages {
        stage('Hello') {
            when{
           	expression{
                   BRANCH_NAME == 'dev-add-users-via-jenkins-job' && CODE_CHANGES == true
                }

            }
            steps {
                echo 'Hello World'
                echo ' this done by M. $AUTHOR'
                /*withCredentials([
                   usernamePassword( credentials: 'add-ssh-users', usernameVariable: USER, passwordVariable: PWD)
                ]){

                   sh " some script $USER ${PWD}"
                }
                */ 
            }
        }
    }
}

