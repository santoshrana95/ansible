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
                    extras: '-i inventory/hosts --private-key /root/.ssh/id_rsa.key -u ec2-user -vvv'
                )
            }
        }
    }
}
