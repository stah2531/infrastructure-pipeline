pipeline {
  agent { label 'linux' }
    stages {
      stage('GetInstances') {
        steps {
          sh "aws ec2 describe-instances --region us-east-1"
        }
      }
      
      stage('CreateInstance') {
        steps {
          sh "env"
        }
      }
    }
}
