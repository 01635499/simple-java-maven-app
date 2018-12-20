pipeline {
  agent any
  
  tools {
    maven 'mvn-3.5.2'
  }
  
  stages {
    stage('Init') {
      steps {
        echo 'Hello World'
         sh 'mvn package'
           
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
      post {
        always {
          junit 'target/surefire-reports/*.xml'
        }
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying'
        sh './jenkins/scripts/deliver.sh'
        
      }
    }
  }
}


