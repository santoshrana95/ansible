pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/yourusername/deployment-project.git'
            }
        }
        stage('Run Ansible Playbook') {
            steps {
                ansiblePlaybook credentialsId: 'ansible-ssh-key',
                    inventory: 'inventory/hosts',
                    playbook: 'playbooks/deploy.yml'
            }
        }
    }
}

