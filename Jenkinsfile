pipeline {
  agent any
  stages {
    stage('Init') {
      steps {
        echo 'Hello World'
      }
    }
    stage('Build') {
      steps {
        sh 'mvn -B -DskipTests clean package'
      }
    }
    stage('test') {
      steps {
        echo '222'
      }
    }
  }
}