pipeline {
   agent any

   triggers{
    pollSCM('* * * * *')
   }

    stages {
        stage('Stage1'){
            when { changeset "Jenkinsfile" } 
            steps{
                echo "Echoing Stage  first 1 "
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