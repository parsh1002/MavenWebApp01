pipeline {
    agent any  

    tools {
        maven 'Maven'  
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/parsh1002/Devopstest_Program3.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'Program3.war', fingerprint: true
            }
        }

        stage('Deploy') {
            steps {
                sh 'mvn clean package'
            }
        }    
    }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
