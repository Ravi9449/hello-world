pipeline {
   agent any

   triggers{
    pollSCM('* * * * *')
   }

   parameters {
    choice(
        name: 'DEPLOY',
        choices: ['integration', 'preprod', 'prod'],
        description: 'stage to deploy to'
    )

    choice(
        name: 'Release',
        choices: ['old', 'new'],
        description: 'type of release'
    )
   }

    stages {
        stage('Stage1'){
            
            steps{
                script{
                    if("$Release" == "new"){
                        echo "${DEPLOY}"
                    }
                    else{
                        echo "Old Release"
                    }
                }
            }
        }

        stage('Stage2'){
            steps{
                echo "Echoing Stage second 2"
            }
        }

        stage('Stage3'){
            steps{
                echo "Echoing Stage third 3"
            }
        }
    }
}

