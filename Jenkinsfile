pipeline {
    agent { label 'MASTER' }
    stages {
        stage('ENV') {
            steps {
                sh 'env > env.txt'
            }
        }
        stage('PROMOTION') {
            steps {
                def userInput = input(
 				id: 'userInput', message: 'Let\'s promote?', parameters: [
 				[$class: 'TextParameterDefinition', defaultValue: 'uat', description: 'Environment', name: 'env'],
 				[$class: 'TextParameterDefinition', defaultValue: 'uat1', description: 'Target', name: 'target']
				])
				echo ("Env: "+userInput['env'])
				echo ("Target: "+userInput['target'])
            }
        }
    }
}
