pipeline {
    agent { label 'MASTER' }
        parameters {
        choice(choices: ['inventory', 'inventorypm'], description: '', name: 'INV_FILE')
        choice(choices: ['all', 'DEV', 'SIT', 'UATSEC', 'PERF', 'PREPROD', 'PROD', 'PRODA', 'PRODB'], description: '', name: 'INV_GRP')
    }
    stages {
        
        stage('API tests'){
            steps {
                echo 'Executing API tests... ya right!!!'
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
