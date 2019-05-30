//def userInput = input(
    //id: 'userInput', message: 'Let\'s promote?', parameters: [
    //[$class: 'TextParameterDefinition', defaultValue: 'uat', description: 'Environment', name: 'env'],
    //[$class: 'TextParameterDefinition', defaultValue: "${TARGET_ENVIRONMENT}", description: 'Target Environment', name: 'target']])

pipeline {
    agent { label 'MASTER' }
        
        parameters {
        choice(choices: ['DEV', 'DEV2', 'DEV3', 'SIT1', 'SIT2', 'UAT', 'UAT2', 'UAT3', 'PERF', 'SEC'], description: '', name: 'TARGET_ENVIRONMENT')

        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
            
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')

        file(name: "FILE", description: "Choose a file to upload")
         
    }
    
    stages {

        // stage('Test crap'){

        //     steps {
        //         echo ("Env: "+userInput['env'])
        //         echo ("Target: "+userInput['target'])
        //     }
        // }
        
        // stage('API tests'){
        //     steps {
        //         echo 'Executing API tests... ya right!!!'
        //         echo ("Env Blah1: "+userInput['env'])
        //         echo ("TARGET_ENVIRONMENT: "+"${TARGET_ENVIRONMENT}")
        //     }
        // }

        stage('Example') {
            steps {
                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
            }
        }
        
        stage('Install Dependencies') {
            steps {
        ansiColor('xterm') {
            sh 'ls -lrat'
               }

            }
        }
    

        stage('Demo Performance'){
            steps {
                echo 'Clap if you liked the demo!'
            }
        }
    }
}    

