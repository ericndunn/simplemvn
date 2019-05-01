pipeline {
    agent { label 'MASTER' }
        
    stages {
        stage('Run Ansible Access operation'){
        
            steps {

            wrap([$class: 'AnsiColorBuildWrapper', colorMapName: "xterm"]) {
                    echo 'Validate Access'
                    //sh 'ansible-playbook -i dev-servers site.yml'
                    ansiblePlaybook credentialsId: '62c93b86-c4ba-483c-a696-8180694ce559',
                    installation: 'ansible', 
                    inventory: '/Users/ag19884/test/ansible_testing/roletest/inventorypm',
                    limit: 'DEV',
                    playbook: '/Users/ag19884/test/ansible_testing/roletest/server_access_status.yml',
                    colorized: true
                }
            }
        }
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
}
