pipeline {
    agent { label 'MASTER' }
        
        parameters {
        choice(choices: ['PROD', 'UAT2'], description: '', name: 'TARGET_ENVIRONMENT')
        choice(choices: ['MCDABCBS', 'MCDLAHB', 'MCDEHP', 'MCDFLS', 'MCDFLC', 'MCDAGP'], description: '', name: 'BRAND')
        string(name: 'CUR_VER', defaultValue: '1.0.0', description: 'What do you want')  
    }
    
    stages {
        stage('Cleanup Workspace') {
            agent {
                label "MASTER"
            }
            steps {
                step([$class: 'WsCleanup'])
            }
        }        
        stage('GIT files') {
            parallel {
                stage('Git Repo1') {
                    agent {
                        label "MASTER"
                    }
                    steps {
                        echo "TARGET ENVIRONMENT: ${params.TARGET_ENVIRONMENT}"
                        echo "BRAND: ${params.BRAND}"
                        echo "CURRENT VERSION: ${params.CUR_VER}"

                        sh 'mkdir -p medicaid-ui-1'
                        dir("medicaid-ui-1")
                        {
                            git branch: "release/Bespin",
                            credentialsId: '62c93b86-c4ba-483c-a696-8180694ce559',
                            url: 'ssh://bitbucket.anthem.com:7999/madt/medicaid-ui.git'
                        }
                    }
                } 
                stage('Git Repo2') {
                    agent {
                        label "MASTER"
                    }
                    steps {
                        echo "TARGET ENVIRONMENT: ${params.TARGET_ENVIRONMENT}"
                        echo "BRAND: ${params.BRAND}"
                        echo "CURRENT VERSION: ${params.CUR_VER}"
                                                
                        sh 'mkdir -p medicaid-ui-1'
                        dir("medicaid-ui-1")
                        {
                            git branch: "develop",
                            credentialsId: '62c93b86-c4ba-483c-a696-8180694ce559',
                            url: 'ssh://bitbucket.anthem.com:7999/madt/medicaid-ui.git'
                        }
                    }
                }                            
            }
        }
    }
}
