pipeline {
    agent any
    //tools { 
        //maven 'maven' 
        //jdk 'jdk8' 
    //}
    stages {
        stage ('Initialize') {
            steps {
               sh '''#!/bin/bash

                    echo "Hello from bash"
                    echo "Who do I $SHELL"
                '''
            }
        }

        stage ('Build') {
            steps {
                sh '/usr/local/bin/mvn install' 
            }
        }
    }
}
