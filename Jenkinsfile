pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'build.sh'
            }
        }
        stage('Test') {
            steps {
                sh 'test.sh'
            }
        }
        stage('Create Service') {
            steps {
                sh 'createService.sh'
            }
        }
        stage('Create Deployment') {
            steps {
                sh 'createDeployment.sh'
            }
        }        
        stage('Deploy') {
            steps {
                sh 'deploy.sh'
            }
        }       
    }

    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}
