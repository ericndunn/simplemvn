pipeline {
    agent { label 'MASTER' }
    stages {
        stage('build') {
            steps {
                sh env > env.txt 
            }
        }
    }
}

