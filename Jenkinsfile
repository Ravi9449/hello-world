#!groovy

pipeline {
   agent any
   parameters {
        gitParameter name: 'TAG',
                     sortMode: 'DESCENDING',
                     type: 'PT_TAG',
                     defaultValue: 'master'
    }
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

 