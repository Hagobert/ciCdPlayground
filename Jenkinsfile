pipeline {
    agent any

    tools {
        nodejs 'yarn'
    }

    stages {
        stage('Build') {
            steps {
                step('Build'){
                    git checkout 'https://github.com/Hagobert/ciCdPlayground'
                    yarn
                    yarn build
                }
            }
        }
        stage('UnitTest'){
            steps{
                step('UnitTest'){
                    yarn test
                }

            }
        }

        stage('IntegrationTest'){
            steps{
                step('IntegrationTest'){
                    yarn build
                    yarn test:e2e
                }
            }
        }
    }
}
