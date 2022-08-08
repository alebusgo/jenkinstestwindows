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
                bat 'gradle clean test aggregate'
             }
        }

        stage("test2") {
            steps {
                echo 'excecuting automated test2'
                bat 'gradle clean test -Denvironment=qa aggregate'

            }
        }

        stage("test3") {
            steps {
                echo 'excecuting automated test3'
                bat 'gradle clean test -Denvironment=prov aggregate'

            }

        }
    }
    post {
        always {
            junit './target/site/serenity/SERENITY-JUNIT-*.xml'
            publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'htmlReport', reportFiles: 'reporte.html', reportName: 'HTML Report', reportTitles: ''])
        }
    }
}









