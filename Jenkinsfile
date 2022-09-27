pipeline {
   agent any

   triggers{
    pollSCM('* * * * *')
   }

    stages {
        stage('Stage1'){
            when { changeset "webapp/*.xml" } 
            steps{
                echo "Echoing Stage second 1"
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