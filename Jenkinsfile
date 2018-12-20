pipeline {
  agent any
  stages {
    stage('Init') {
      steps {
        echo 'Hello World'
           getDockerImage('maven:3.2').inside {
            sh 'mvn -v'
          }
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
