properties([pipelineTriggers([githubPush()])])
node('linux') {
    git url: 'https://github.com/stah2531/infrastructure-pipeline.git', branch: 'master'
    stage('Test') {
        sh "env"
    }
    
    stage('GetInstances') {
        sh "aws ec2 describe-instances --region us-east-1"   
    }
          
    stage('CreateInstance') {
        sh "aws ec2 run-instances --image-id ami-013be31976ca2c322 --count 1 --instance-type t2.micro --key-name SEIS665_securitygroup --security-group-ids sg-54675818 --subnet-id subnet-d8aa27f6 --region us-east-1"    
    }
}
