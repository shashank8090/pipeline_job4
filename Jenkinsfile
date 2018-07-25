pipeline {
  agent {
    docker {
      image 'Maven:3.3.9-jdk-8'
    }

  }
  stages {
    stage('Initialize') {
      agent {
        docker {
          image 'Maven:3.3.9-jdk-8'
          args '-v/Users/bitwiseman/.m2:/root/.m2'
        }

      }
      steps {
        sh '''echo PATH = ${PATH}











                   

      

'''
      }
    }
    stage('build') {
      steps {
        sh 'mvn -Dmaven.test.failure.ignore=true install'
      }
    }
    stage('report') {
      steps {
        junit 'target/surefire-reports/**/.xml'
      }
    }
  }
}