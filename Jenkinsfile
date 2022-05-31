pipeline {
    agent any
    environment {
        COMMIT_ID = sh(returnStdout: true, script: 'git rev-parse HEAD')
        IMAGE_TAG = "JENKINS-${env.BUILD_ID}_${BRANCH_NAME}_${COMMIT_ID}"
    }
    stages {
        stage('Build and Run') {
            steps {
                sh '''
                    echo $IMAGE_TAG
                    echo "=================="
                    docker-compose -f docker-compose.yml -f docker-compose.dev.yml up -d
                '''
            }
        }
    }

  post {
    failure {
      script {
        mail(to: 'admin@rayuni.com',
          subject: "Job '${env.JOB_NAME}' (${env.BUILD_NUMBER}) failed.",
          body: "Please visit ${env.BUILD_URL} for further information."
        );
      }
    }
  }
}
