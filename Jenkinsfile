pipeline{
    agent any
    stages{
        stage('build'){
            step{
                sh 'npm install'
            }
        }
        stage('deploy'){
            steps{
                nodejs(nodeJSInstallationName: 'nodejs'){
                    withAWS(credentials: 'aws-credentials'){
                        sh 'serverless deploy'
                    }
                }
            }
        }
    }
}