//def userInput = input(
    //id: 'userInput', message: 'Let\'s promote?', parameters: [
    //[$class: 'TextParameterDefinition', defaultValue: 'uat', description: 'Environment', name: 'env'],
    //[$class: 'TextParameterDefinition', defaultValue: "${TARGET_ENVIRONMENT}", description: 'Target Environment', name: 'target']])

pipeline {
    agent { label 'MASTER' }
        
        parameters {
        choice(choices: ['PROD', 'UAT2'], description: '', name: 'TARGET_ENVIRONMENT')
        choice(choices: ['MCDABCBS', 'MCDLAHB', 'MCDEHP', 'MCDFLS', 'MCDFLC', 'MCDAGP'], description: '', name: 'BRAND')

        string(name: 'CUR_VER', defaultValue: '1.0.0', description: 'What do you want')

        // text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        // booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        // choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
            
        // password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')

        // file(name: "FILE", description: "Choose a file to upload")
         
    }
    
    stages {

        stage('Example') {
            steps {
                git branch: 'release/Bespin', credentialsId: '62c93b86-c4ba-483c-a696-8180694ce559', poll: false, url: 'ssh://bitbucket.anthem.com:7999/madt/medicaid-ui.git'
                
                echo "Hello ${params.TARGET_ENVIRONMENT}"

                echo "Biography: ${params.BRAND}"

                echo "Toggle: ${params.CUR_VER}"

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

