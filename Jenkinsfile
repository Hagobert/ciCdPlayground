pipeline {
    agent any

    tools {
        nodejs 'yarn'
    }

    stages {
        stage('Build') {
            steps {
                git 'https://github.com/Hagobert/ciCdPlayground'
                sh 'yarn'
                sh 'yarn build'
            }
        }
        stage('UnitTest'){
            steps{
                    sh 'yarn test'
            }
        }

        stage('IntegrationTest'){
            steps{
                    sh 'yarn build'
                    sh 'yarn test:e2e'
            }
        }
    }
}
