pipeline {
    agent any
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
            post {
                failure {
                    error("La prueba falló, no se ejecutará la aplicación.")
                }
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
