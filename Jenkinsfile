pipeline {
   agent any
   triggers {
        pollSCM('* * * * *')
   }
   stages {
      stage('Stage1'){
         steps{
            script{
              echo "Hello world in QA check 1"
            }
         }
      }
   }   
}
