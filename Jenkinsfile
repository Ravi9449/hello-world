pipeline {
   agent any
   //triggers {
   //     pollSCM('* * * * *')
   //}
   tools {
      maven 'maven'
   }
   stages {
      stage('Stage1'){
         steps{
            script{
               echo "${currentBuild.projectName}"
            }
         }
      }

   } 
}

