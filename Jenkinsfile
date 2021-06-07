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
          //    extras: "-u amalonga ",
              credentialsId: 'ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDfuYHMslZcMgrI1htDZSvsekbUngRYcwRPtP28nEhA6/1niE3H+xqO0o307/R8bUY2Z8P58lenZ2hhD6PVIdOAqDWwOeR0RDJ7O188dBjo1csnMuKjjG5sNyYbOnqbneEMgJzKdYEl5QO4zzbMONktjBgmN/N9C2UQw9oBzVg7O2/wN/iT1+TwR6TPoBwvOritndk4ohxv4M3z3lKvr8gRBkkHs0m04GiqJjZvdznJQP84mLY9T4x99JLBLF+2oUW5aV6cNGFFughbqa4NcrDlsaNj9cZleKhaqFIUcMud0pPgciXBIJQJXoXvOKlyfW/9/AfBWWJCm7rb4uzwoT/f amalonga@amalonga-XPS-15-9570',
              colorized: true,
//              become: true,
            )
           //}
         } 
        }
      }
    }
   
}
