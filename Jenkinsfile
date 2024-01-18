pipeline {
  agent {
    label 'slave3'
  }
  stages {
    stage('checkout') {
      steps {
        sh 'rm -rf bus_booking.git'
        sh 'git clone https://github.com/yatheesh2328/bus_booking.git'
      }
    }
    stage('build') {
      steps {
        sh 'mvn --version'
        sh 'mvn clean install'
      }
    }
    stage('deploy') {
      sh 'scp /home/slave3/workspace/demoMBP1_develop/target/bus-booking-app-1.0-SNAPSHOT.jar root@172.31.17.229:/opt/apache-tomcat-8.5.98/webapps/'
  }
}
}
}
