pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the application ...'
                bat 'gradle clean build -x test'

            }
        }
        stage("test1") {
             steps {
                echo 'excecuting automated test1'
                bat 'gradle clean test aggregate'
             }
        }
    }
    post {
        always {
            junit '/target/site/serenity/index.html'
        }
    }
}









