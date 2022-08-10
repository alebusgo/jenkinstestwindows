pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the application ...'
                withGradle(){
                    bat 'gradlew clean build -x test'
                    bat 'gradle clean test aggregate'
                }
            }
        }
    }
}









