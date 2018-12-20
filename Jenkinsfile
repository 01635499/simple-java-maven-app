pipeline {
   agent {
        docker {
            image 'maven:3-alpine' 
            args '-v /root/.m2:/root/.m2' 
        }
  }
  
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


