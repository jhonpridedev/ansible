pipeline {
    agent {
        docker {
            image 'quay.io/ansible/ansible-runner:stable-2.12-latest'
            args '-u root'
        }
    }
    stages {
        stage('ansible') {
            steps {
                
                sh 'cat /etc/os-release'

                sh 'whoami'

                sh 'ansible --version'
            }
        }
    }
}