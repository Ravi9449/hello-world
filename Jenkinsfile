pipeline {
   agent any
   triggers {
        pollSCM('* * * * *')
   }
   stages {
      stage('Stage1'){
         steps{
            script{
               echo "Hello World in Master check 1"
            }
         }
      }

      stage('Add tag name'){
         steps{
            scripts{
               sh git tag v3.0 
            }
         }
      }  
   } 
}

