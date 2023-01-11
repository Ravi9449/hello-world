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

      stage('get pom version'){
         steps{
            script{
               sh "mvn build-helper:parse-version versions:set -DnewVersion=\${parsedVersion.majorVersion}.\${parsedVersion.minorVersion}.\${parsedVersion.nextIncrementalVersion} versions:commit"
            }
         }
      } 
   } 
}

