pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/santoshrana95/ansible.git',
                    credentialsId: 'ansible-ssh-key'
            }
        }

        stage('Run Ansible Playbook') {
            steps {
                ansiblePlaybook(
                    playbook: 'playbooks/deploy.yml',
                    inventory: 'inventory/hosts',
                    credentialsId: 'ec2-user'
                )
            }
        }
    }
}
