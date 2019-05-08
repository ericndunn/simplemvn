pipeline {
    agent { label 'MASTER' }
    stages {
        stage('build') {
            steps {
                sh 'env > env.txt' 
				for (String i : readFile('env.txt').split("\r?\n")) {
    			println i
				}
            }
        }
    }
}
