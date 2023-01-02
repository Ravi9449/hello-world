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
               def script_output = sh(returnStdout: true, script: """
                  version_line=$(cat pom.xml | grep "<version>" | head -1)
                  version=${version_line#*>}
                  echo \$pomversion=${version%-*}
               """)
               // script_output = script_output.trim()
               // VAR_NAME = script_output
               // echo "VAR_NAME is ${VAR_NAME}"
               // sh script: '''
               // version_line=$(cat pom.xml | grep "<version>" | head -1)
               // echo ${version_line}
               // version=${version_line#*>}
               // echo ${version}
               // pomversion=${version%-*}
               // ''', returnStatus: true

               echo "${pomversion}"
               
               // sh 'version_line=$(cat pom.xml | grep "<version>" | head -1)'
               // sh 'version=${version_line#*>}'
               // sh 'echo pomversion="${version%-*}"'
               // echo "${pomversion}"

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

