pipeline {
    agent {
        docker {
            image 'quay.io/ansible/ansible-runner:stable-2.12-latest'
            args '-u root'
        }
    }
    environment {
        ANSIBLE_HOST_KEY_CHECKING = 'False'
    }
    stages {
        stage('ansible') {
            steps {
                
                sh 'cat /etc/os-release'

                sh 'whoami'

                sh 'ansible --version'
                
                sshagent (credentials: ['debian-private-key']) {
                    
                    sh 'ansible server1 -i hosts -a "cat /etc/os-release" -u admin'

                    // sh 'ansible server1 -i hosts -m yum -a "name=wget state=latest" -u admin --become'

                    // sh 'ansible server4 -i hosts -m yum -a "name=nmap state=latest"'

                    // // sh 'ansible server1 -i hosts -m yum -a "name=java-17-openjdk state=latest" -u admin --become'

                    // sh 'ansible-inventory -i hosts --list -y'

                    // sh 'ansible-playbook -i hosts playbooks/server1_config.yml'

                    // sh 'ansible-playbook -i hosts playbooks/server1_jboss.yml'
                }
                
            }
        }
    }
}