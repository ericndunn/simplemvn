def userInput = input(
    id: 'userInput', message: 'Let\'s promote?', parameters: [
    [$class: 'TextParameterDefinition', defaultValue: 'DEV', description: 'TARGET_ENVIRONMENT', name: 'TARGET_ENVIRONMENT']])

pipeline {
    agent { label 'MASTER' }
        parameters {
        choice(choices: ['DEV', 'DEV2', 'DEV3', 'SIT1', 'SIT2', 'UAT', 'UAT2', 'UAT3', 'PERF', 'SEC'], description: 'ENVIRONMENT', name: 'ENVIRONMENT')
    }
    stages {

        stage('Test crap'){

            steps {
                echo ("Target: "+userInput['TARGET_ENVIRONMENT'])
            }
        }
        
        stage('API tests'){
            steps {
                echo 'Executing API tests... ya right!!!'

                echo ("Target Blah2: "+userInput['TARGET_ENVIRONMENT'])
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
    
    
