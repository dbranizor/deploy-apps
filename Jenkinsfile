


ansiblePlaybook(credentialsId: 'private_key', inventory: 'inventories/a/hosts', playbook: 'my_playbook.yml')


pipeline { 
    agent any
    stages {
        stage ('Deploy Web') {
            steps {
                ansiblePlaybook('ansible/site.yml') {
                    inventoryPath('environments/dev')
                    ansibleName('1.9.4')
                    tags('web')
                    credentialsId('ssh-ansible')
                    become(true)
                    becomeUser("elquico")
                    vaultCredentialsId("ansible-vault")
                }
            }
        }

    }
}