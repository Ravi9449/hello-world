pipeline {
   agent any

   triggers{
    pollSCM('* * * * *')
   }

   parameters {
    choice(
        name: 'STAGE',
        choices: ['integration', 'preprod', 'prod'],
        description: 'stage to deploy to'
    )
   }

    stages {
        stage('Stage1'){
            
            steps{
                echo "$STAGE"
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

