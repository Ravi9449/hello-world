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
   }

    stages {
        stage('Stage1'){
            
            steps{
                echo "${DEPLOY}"
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

