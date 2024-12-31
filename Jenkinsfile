pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/santoshrana95/ansible.git'
            }
        }
        stage('Run Ansible Playbook') {
            steps {
                git credentialsId: 'github-token', url: 'https://github.com/santoshrana95/ansible.git',
                    inventory: 'inventory/hosts',
                    playbook: 'playbooks/deploy.yml'
            }
        }
    }
}

