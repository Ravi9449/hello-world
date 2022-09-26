pipeline {
   agent any

   triggers{
    pollSCM('* * * * *')
   }

    stages {
        stage('Stage1'){
            steps{
                echo "Echoing Stage  first 1 "
            }
        }

        stage('Stage2'){
            steps{
                echo "Echoing Stage 2"
            }
        }

        stage('Stage3'){
            steps{
                echo "Echoing Stage 3"
            }
        }
    }
}