pipeline {
    agent any
      stages {
        stage('Build') { 
            steps {
            sh '''
            sudo docker build -t 192.168.0.41:5000/project:web .
            '''
            }
        }
        stage('Push') { 
            steps {
            sh '''
            sudo docker push 192.168.0.41:5000/project:web
            '''    
            }
        }
        stage('apply') { 
            steps {
            sh '''
            sudo kubectl apply -f hello.yml
            '''    
            }
        }
    }
}
