node {
stage 'promotion'
def userInput = input(
    id: 'userInput', message: 'Let\'s promote?', parameters: [
    [$class: 'TextParameterDefinition', defaultValue: 'uat', description: 'Environment', name: 'env'],
    [$class: 'TextParameterDefinition', defaultValue: 'uat1', description: 'Target', name: 'target']])

pipeline {
    agent { label 'MASTER' }
        parameters {
        choice(choices: ['inventory', 'inventorypm'], description: '', name: 'INV_FILE')
        choice(choices: ['all', 'DEV', 'SIT', 'UATSEC', 'PERF', 'PREPROD', 'PROD', 'PRODA', 'PRODB'], description: '', name: 'INV_GRP')
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
                echo ("Target Blah2: "+userInput['target'])
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
    

}
