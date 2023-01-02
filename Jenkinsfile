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
               // sh script: '''version_line=$(cat pom.xml | grep "<version>" | head -1)
               // echo "${version_line}"
               // version=${version_line#*>}
               // echo "${version}"
               // env.pomversion=${version%-*}''', returnStdout: true
               sh "ls"
               sh "version_line=$(cat pom.xml | grep "<version>" | head -1)"

            }
         }
      }

      stage('check pom version'){
         steps{
            script{
               echo "${pomversion}"
            }
         }
      }  
   } 
}

