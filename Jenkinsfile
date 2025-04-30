def workspace
node {
    stage('Checkout')
    {
checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Tigers83/self-learning.git']])    
    }
    stage('Code Analysis')
    {
        build job: 'Code Analysis', parameters: [string(name: 'workspace', value: '')]
    }

    
}


