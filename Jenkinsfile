
pipeline {
    agent any
    environment{
     RAUTHOR='amalonga'
     // SERVER_CREDENTIALS = credentials('add-ssh-users')
      
    }
    stages {
        stage('git source') {
            steps {
                echo 'Hello World'
                echo ' this done by M. ${AUTHOR} '
                git branch: 'params.dev-add-users-via-jenkins-job', url: 'https://github.com/amalonga/amalonga.git'
            }
        }
    }
}

