pipeline {
    agent any
    //tools { 
        //maven 'maven' 
        //jdk 'jdk8' 
    //}
    stages {
          stage ('Initialize') {
            steps {
                sh '''
                   env > env.txt
                   for (String i : readFile('env.txt').split("\r?\n")) {
                   println i
                ''' 
            }
        }

        stage ('Build') {
            steps {
                sh '/usr/local/bin/mvn verify' 
            }
        }
        
        stage ('TEST') {
            steps {
                sh 'env > env.txt' 
                for (String i : readFile('env.txt').split("\r?\n")) {
                println i
              }
            }
        } 
        }
    }
}
