pipeline {
    agent any
    
        tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "maven363"
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh "mvn install"
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}

/*node {
    def os = System.properties['os.name'].toLowerCase()
    echo "OS: ${os}"
    if (os.contains("linux")) {
      sh "mvn install" 
    } else {
      bat "mvn install"
    }
}
*/
