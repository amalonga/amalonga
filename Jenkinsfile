def ENVIRONMENT_LIST = ['int', 'cus']

// Ansible's parameters
def repository = "https://github.com/amalonga/amalonga.git" // SSH url (not HTTPS)
def credentialsId = "add-ssh-users" 
def vaultCredentialsId = "ansible-vault" // This is a jenkins credential, which refer to --vault-password-file parameter
def inventory = "inventory"
def playbook = "debug_module_test.yml" // We will use deploy.yml instead of datahub.yml when "killing" bot platform
def AUTHOR = "amalonga"

pipeline{
    agent any
    stages {
        stage('git source') {

            steps {
                echo 'Hello World'
                echo ' this done by M. AUTHOR '
                git branch: 'dev-add-users-via-jenkins-job', url: repository, credentialsId: credentialsId
            }
        }
        
      stage('INT | Run Ansible without extra ENV_VAR') {

      steps {
        // Run the playbook using the custom version
          ansiColor('xterm') {
            ansiblePlaybook(
              playbook: playbook,
              inventory: inventory,
          #    extras: "-u amalonga ",
              credentialsId: credentialsId,
              colorized: true,
              become: true,
            )
           //}
         } 
        }
      }
    }
   
}
