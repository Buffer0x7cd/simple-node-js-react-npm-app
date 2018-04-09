pipeline{
    agent {
        docker {
            image 'node:6-alpine'
            args '-p 3000:3000' 
        }
    }
    stages{
        stage('Checkout'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/Buffer0x7cd/simple-node-js-react-npm-app.git']]])
            }
        }
        stage('Project Directory'){
            sh 'cd simple-node-js-react-npm-app'
        }
        stage('Build'){
            steps{
                sh 'npm install'
            }
        }
    }
}