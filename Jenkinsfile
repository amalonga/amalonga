
def AUTHOR = 'cool Amel '

pipeline {
    agent any
    environment{
     RAUTHOR='amalonga'
     // SERVER_CREDENTIALS = credentials('add-ssh-users')
      
    }
    parameters {
        
    }
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
                echo ' this done by M. ${AUTHOR} '
		git url: 'https://github.com/amalonga/amalonga.git', branch: 'params.dev-add-users-via-jenkins-job'

        }
    }
}

