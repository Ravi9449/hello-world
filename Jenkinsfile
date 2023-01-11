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
               echo "${readPom.version.replace('*-SNAPSHOT', '')}"
            }
         }
      }

   } 
}

