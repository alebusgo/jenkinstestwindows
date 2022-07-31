pipeline {

    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the application ...'
                sh 'gradle clean build -x test'
            }
        }

        stage("test") {
             steps {
                echo 'executing automated test'

             }
        }
    }
}









