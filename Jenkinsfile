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
    stage('Test') {
      steps {
        echo '222'
        sh 'mvn test'
      }
    }
  }
}
