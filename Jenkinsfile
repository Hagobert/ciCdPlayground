pipeline {
    agent any

    tools {
        nodejs 'yarn'
    }

    stages {
        stage('Build') {
            steps {
                git checkout 'https://github.com/Hagobert/ciCdPlayground'
                yarn
                yarn build
            }
        }
        stage('UnitTest'){
            steps{
                yarn test
            }
        }
        
        stage('IntegrationTest'){
            steps{
                yarn build
                yarn test:e2e
            }
        }
    }
}
