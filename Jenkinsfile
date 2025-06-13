pipeline {
    agent any

    tools {
        maven 'Maven 3.8.6'
        jdk 'JDK11'
    }

    stages {
        stage('Clonar') {
            steps {
                git 'https://github.com/gerardbourguett/saludoapp.git'
            }
        }

        stage('Compilar') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Empaquetar') {
            steps {
                sh 'mvn package'
            }
        }
    }

    post {
        success {
            echo " El build fue exitoso" 
        }

        failure {
            echo " El build fallo"
        }
    }
}