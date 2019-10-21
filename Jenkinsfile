pipeline {
  agent  {
    label "jenkins-maven"
  }
  options {
      skipStagesAfterUnstable()
  }
  stages {
    stage('Build') {
      steps {
        container('maven') {
          sh 'mvn -B -DskipTests clean package'
        }
      }
    }
    stage('Test') {
      steps {
        container('maven') {
          sh 'mvn test'
        }
      }
      post {
          always {
              junit 'target/surefire-reports/*.xml'
          }
      }
    }
    stage('Deliver') {
        steps {
        container('maven') {
            sh './jenkins/scripts/deliver.sh'
        }
      }
    }
  }
}