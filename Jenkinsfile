pipeline {
   agent any

   triggers{
    pollSCM('')
   }

    stages {
        stage('Stage1'){
            steps{
                echo "Echoing Stage 1"
            }
        }

        stage('Stage2'){
            steps{
                echo "Echoing Stage 12"
            }
        }
    }
}