pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Test SSH Connection') {
            steps {
                dir('ansible') {
                    sh '''
                        ansible webservers -m ping -i inventory.ini
                    '''
                }
            }
        }
        
        stage('Deploy NGINX') {
            steps {
                dir('ansible') {
                    sh '''
                        ansible-playbook -i inventory.ini playbook.yml
                    '''
                }
            }
        }
        
        stage('Verify NGINX') {
            steps {
                dir('ansible') {
                    sh '''
                        ansible webservers -m shell -a "curl -s http://localhost" -i inventory.ini
                    '''
                }
            }
        }
    }
    
    post {
        success {
            echo 'NGINX deployed successfully!'
        }
        failure {
            echo 'Deployment failed. Check logs above.'
        }
    }
}
