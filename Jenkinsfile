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
               readPom = readMavenPom file:'pom.xml'
               RELEASE_BRANCH = sh script : 'echo ${readPom}', returnStdout: true
               echo "${RELEASE_BRANCH}"
            }
         }
      }

   } 
}

