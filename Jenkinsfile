node {
    stage('Checkout')
    {
    checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Tigers83/self-learning.git']])    
    }
    stage('Code Compile')
    {
    build job: 'Code Compile', parameters: [string(name: 'workspace', value: '')]
    }
    stage('Code Unity Test')
    {
        build job: 'Code Unit Test', parameters: [string(name: 'workspace', value: '')]
    }
    stage('Code Package')
    {
        build job: 'Code Package', parameters: [string(name: 'workspace', value: '')]
    }
    stage('Code Deploy')
    {
        build 'Code Deploy' 
    }

}


