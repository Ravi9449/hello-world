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
            scripts{
               sh version_line=$(cat pom.xml | grep "<version>" | head -1)
               echo $"{version_line}"

               sh version=${version_line#*>} 
 
               echo $"{version}"

               sh pomversion=${version%-*}

               echo $"{pomversion}"
            }
         }
      }

      stage(check pom version){
         steps{
            script{
               echo $"{pomversion}"
            }
         }
      }  
   } 
}

