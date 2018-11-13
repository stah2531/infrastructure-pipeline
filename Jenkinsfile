properties([pipelineTriggers([githubPush()])])
node('linux') {
    git url: 'https://github.com/stah2531/infrastructure-pipeline.git', branch: 'master'
    stage('Test') {
        sh "env"
    }
}
