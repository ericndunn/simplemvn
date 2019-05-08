pipeline {
    agent any
    stages {
          stage ('Initialize') {
            steps {
                sh '''
                   env > env.txt
                   #for (String i : readFile('env.txt').split("\r?\n")) {
                   #println i
                ''' 
            #}
        }
        stage ('Build') {
            steps {
                sh '/usr/local/bin/mvn verify' 
            }
        }
    }
}
