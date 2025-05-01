node {

    environment {
        SONAR_SCANNER_HOME = tool 'sonarqube-scanner-610';
    }

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
stage('SAST - SonarQube') {
    sh '''
        echo $SONAR_SCANNER_HOME
        $SONAR_SCANNER_HOME/bin/sonar-scanner \
            -Dsonar.projectKey=Solar-System-Project \
            -Dsonar.sources=. \
            -Dsonar.host.url=http://localhost:9000 \
            -Dsonar.login=sqp_3024dde79b3d62f92c1b50be365c45de0817dd9c
    '''
}


    stage('Code Deploy')
    {
        build 'Code Deploy' 
    }
}


