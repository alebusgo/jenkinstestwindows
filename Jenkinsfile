pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the application ...'
                withGradle(){
                    bat 'gradlew clean build -x test'
                }

            }
        }
        stage("test1") {
             steps {
                echo 'excecuting automated test1'
                bat 'gradlew clean test aggregate'
             }
        }
    }
    post {
        always {
            junit 'target/site/serenity/SERENITY-JUNIT_*.xml'
            publishHTML target: [
            allowMissing: false,
            alwaysLinkToLastBuild: false,
            keepAll: false,
            reportDir: 'target/site/serenity/',
            reportFiles: 'index.html',
            reportName: 'HTML Report',
            reportTitles: ''
            ]
        }
    }
}









