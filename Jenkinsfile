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
               RELEASE_BRANCH = sh script : 'echo ${readPom.version}', returnStdout: true
               echo "${RELEASE_BRANCH}"
            }
         }
      }

   } 
}

