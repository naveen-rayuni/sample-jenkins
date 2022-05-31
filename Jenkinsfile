pipeline {
    agent any
    stages {
        stage('Build and Run') {
            steps {
                sh '''
                    docker-compose -f docker-compose.yml -f docker-compose.dev.yml up -d
                '''
            }
        }
    }
}
