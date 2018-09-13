pipeline {
<<<<<<< HEAD
    agent {
        docker {
            image 'maven:3-alpine'
            args '-u 1000 -e MAVEN_CONFIG=/var/maven/.m2 -v /home/thor/.m2:/var/maven/.m2'
        }
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'mvn -B -DskipTests clean package'
      }
    }
    stage('Test') {
      post {
        always {
          junit 'target/surefire-reports/*.xml'

        }

      }
      steps {
        sh 'mvn test'
      }
    }
    stage('Deliver') {
      steps {
        sh './jenkins/scripts/deliver.sh'
      }
    }
  }
}
