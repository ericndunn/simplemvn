pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
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
