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
                echo "Echoing Stage second 2"
            }
        }

        stage('Stage3'){
            when { changeset "Jenkinsfile"} //Will execute your steps if any file change inside the component_a directory
            steps{
                echo "Echoing Stage third 3"
            }
        }
    }
}