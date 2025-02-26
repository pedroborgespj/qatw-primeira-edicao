pipeline {
    agent {
        docker {
            image 'pedroborgespj/playwright-nj-v1.50.1-noble'
            args '--network qatw-primeira-edicao_skynet'
        }
    }

    stages {
        stage('Node.js Deps') {
            steps {
                sh 'yarn install'
            }
        }
        stage('E2E Tests') {
            steps {
                sh 'yarn playwright test'
                allure includeProperties: false, jdk: '', results: [[path: 'allure-results']]
            }
        }
    }
}
