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
          output = sh returnStdout: true, script: 'aws ec2 run-instances --image-id ami-009d6802948d06e52 --count 1 --instance-type t2.micro --key-name SEIS665_securitygroup --security-group-ids sg-54675818 --subnet-id subnet-d8aa27f6 --region us-east-1'
          sh "aws ec2 wait --region us-east-1 instance-running --instance-ids $output"
        }
      }
    
      stage('TerminateInstance') {
        steps {
          sh "aws ec2 terminate-instances --region us-east-1 --instance-ids $output"
        }
      }
    }
}
