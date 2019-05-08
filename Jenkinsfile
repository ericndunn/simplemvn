def userInput = input(
    id: 'userInput', message: 'Let\'s promote?', parameters: [
    [$class: 'TextParameterDefinition', defaultValue: 'uat', description: 'Environment', name: 'env'],
    [$class: 'TextParameterDefinition', defaultValue: "${TARGET_ENVIRONMENT}", description: 'Target Environment', name: 'target']])

pipeline {
    agent { label 'MASTER' }
        parameters {
        choice(choices: ['DEV', 'DEV2', 'DEV3', 'SIT1', 'SIT2', 'UAT', 'UAT2', 'UAT3', 'PERF', 'SEC'], description: '', name: 'TARGET_ENVIRONMENT')
    }
    stages {

        stage('Test crap'){

            steps {
                echo ("Env: "+userInput['env'])
                echo ("Target: "+userInput['target'])
            }
        }
        
        stage('API tests'){
            steps {
                echo 'Executing API tests... ya right!!!'
                echo ("Env Blah1: "+userInput['env'])
                echo ("TARGET_ENVIRONMENT: "+"${TARGET_ENVIRONMENT}")
            }
        }

        stage('Performance tests'){
            steps {
                echo 'Wow! Wicked Fast!!!'
            }
        }

        stage('Demo Performance'){
            steps {
                echo 'Clap if you liked the demo!'
            }
        }
    }
}
