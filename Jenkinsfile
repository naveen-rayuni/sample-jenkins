pipeline {
    agent any
    stages {
        stage('verify tooling') {
            steps {
                sh '''
                    docker-compose -f docker-compose.yml -f docker-compose.dev.yml up -d
                '''
            }
        }
    }
}
