pipeline {
    agent any

    stages {
        stage('Git checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/shamayadav/ansible.git']]])
            }
        }
        stage('Invoke Ansible Playbook') {
            steps {
                ansiblePlaybook credentialsId: 'ansiblesshkey', installation: 'ansible', inventory: 'dev.inv', playbook: 'apache.yml'
            }
        }
    }
}
