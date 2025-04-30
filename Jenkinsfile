def workspace
node {
    stage('Checkout')
    {
checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Tigers83/self-learning.git']])
    }
        stage('Static Code Analysis')
    {
        echo "Static Code Analysis"
    }
    stage('Build')
    {
        echo "Build the code"
    }
    stage('Unit Testing')
    {
        echo 'Unit Testing'
    }
    stage('Delivery')
    {
        echo 'Delivery of the code'
    }
}
