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
<<<<<<< HEAD
            junit 'target/site/serenity/SERENITY-JUNIT_*.xml'
             publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'target/site/serenity/', reportFiles: 'index.html', reportName: 'HTML Report', reportTitles: ''])
=======
            junit '.**/target/site/serenity/SERENITY-JUNIT_*.xml'
>>>>>>> 83a25d5f0dff9ab3b7884868e3d83627de0f339b
        }
    }
}









