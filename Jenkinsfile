pipeline {
    agent any
    triggers { 
        githubPullRequest() 
    }
    tools {
        nodejs 'nodejs21'
    }
    stages {
        stage('Build') {
            steps {
                echo "Ejecutar npm install" 
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                echo "Ejecutar npm test push" 
                sh 'npm test'
            }
        }
        stage('Start') {
            steps {
                echo "Ejecutar npm start" 
                sh 'npm start > /dev/null 2>&1 &'
                sh 'sleep 10'
            }
        }
        stage('Request') {
            steps {
                echo "Ejecutar request" 
                sh 'curl http://localhost:3000'
            }
        }
    }
    post {
        always {
            echo "Parar la aplicación"
            sh 'pkill -f "node"'
        }
    }
}
