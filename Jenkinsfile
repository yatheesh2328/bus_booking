@Library('library-demo') _

pipeline {
    agent { label 'java' }
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
                    build()
                }
            }
        }
    }
}
