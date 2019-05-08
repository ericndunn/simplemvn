pipeline {
    agent { label 'MASTER' }
    stages {
        stage('ONE') {
            steps {
                sh 'env > env.txt' 
				}
            }
        }
        stage('TWO') {
            steps {
                sh '''
                for (String i : readFile('env.txt').split("\r?\n")) {
    		println i
		}
		'''
            }
        }
    }

