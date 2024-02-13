@Library('library-demo') _

pipeline {
    agent any
    stages {
        stage('checkout') {
            steps {
                sh 'rm -rf bus_booking'
                sh 'git clone https://github.com/yatheesh2328/bus_booking.git'
            }
        }

        stage('build') {
            steps {
                script {
                    sh 'mvn clean install'
                }
            }
        }
        stage('Sonarqube Scan') {
            steps {
            withSonarQubeEnv('sonar'){
                script {
                    sonar()
                }
            }
            }
        }
    }
}
