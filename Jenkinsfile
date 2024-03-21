pipeline {
    agent any
    // agent {
    //     docker {
    //         image 'quay.io/ansible/ansible-runner:stable-2.12-latest'
    //         args '-u root'
    //     }
    // }
    // environment {
    //     ANSIBLE_HOST_KEY_CHECKING = 'False'
    // }
    stages {
        stage('ansible') {
            steps {
                
                sh 'cat /etc/os-release'

                sh 'whoami'

                sh 'ansible --version'

                sshagent (credentials: ['debian-private-key']) {
                    
                sh 'ansible server1 -i hosts -a "cat /etc/os-release" -u admin'
                }

                // sh 'ansible server1 -m command -a "cat /etc/os-release" -u admin'
                
            }
        }
    }
}