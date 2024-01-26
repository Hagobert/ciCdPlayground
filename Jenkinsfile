pipeline {
    agent any

    tools {
        nodejs 'yarn'
    }

    stages {
        stage('Build') {
            steps {
                step('Build'){
                    git 'https://github.com/Hagobert/ciCdPlayground'
                    sh 'yarn'
                    sh 'yarn build'
                }
            }
        }
        stage('UnitTest'){
            steps{
                step('UnitTest'){
                    sh 'yarn test'
                }

            }
        }

        stage('IntegrationTest'){
            steps{
                step('IntegrationTest'){
                    sh 'yarn build'
                    sh 'yarn test:e2e'
                }
            }
        }
    }
}
