pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git url: 'https://github.com/iammay786/Jenkinsproject.git', branch: 'main'
            }
        }

        stage('Deploy using Ansible Plugin') {
            steps {
                ansiblePlaybook(
                    playbook: 'ansidocker/deploy.yml',
                    inventory: 'ansidocker/hosts.ini',
                    credentialsId: 'ssh-key-id',
                    disableHostKeyChecking: true
                )
            }
        }
    }
}
