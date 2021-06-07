
 CODE_CHANGES = getGitChanges()
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
                echo ' \nthis done by M. $AUTHOR'
                withCredentials([
                   usernamePassword( credentials: 'add-ssh-users', usernameVariable: USER, passwordVariable: PWD)
                ]){

                   sh " some script $USER ${PWD}"
                }
                 
            }
        }
    }
}

