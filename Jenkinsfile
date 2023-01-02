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
               // sh '''
               // version_line=$(cat pom.xml | grep "<version>" | head -1)
               // echo "${version_line}"
               // version=${version_line#*>}
               // echo "${version}"
               // env.pomversion=${version%-*}
               // ''', returnStdout: true
               
               sh 'version_line=$(cat pom.xml | grep "<version>" | head -1)'
               sh 'version=${version_line#*>}'
               sh 'pomversion=${version%-*}'
               echo "${pomversion}"

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

