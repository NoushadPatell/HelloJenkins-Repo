pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/NoushadPatell/HelloJenkins-Repo.git'
            }
        }
        
        stage('Build') {
            steps {
                sh 'chmod +x build.sh'
                sh './build.sh'
            }
        }
        
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'java HelloWorld'
            }
        }
        
        stage('Archive') {
            steps {
                archiveArtifacts artifacts: '*.class', allowEmptyArchive: true
            }
        }
    }
    
    post {
        always {
            echo 'Pipeline completed!'
        }
        success {
            echo 'Build succeeded!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
