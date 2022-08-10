pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the application ...'
                withGradle(){
                    bat 'gradle clean test aggregate'
                }
            }
        }
    }
}









