 pipeline{
  agent { label 'devnode' }
  tools {nodejs "nodejs"}
    stages{   
        stage('Build and Deploy Polaris UI') {
            when {
                expression { env.CHANGE_TARGET == 'development'  }
            }
            steps{
                sh 'pwd'
                sh "yarn install"
                sh "yarn build"
                sh "aws s3 cp build s3://dev-polaris-portal-bucket --recursive"
            }
        }
    }
 }
