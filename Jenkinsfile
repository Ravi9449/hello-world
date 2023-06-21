#!groovy

properties([
    parameters([
        [$class: 'ChoiceParameter',
            choiceType: 'PT_SINGLE_SELECT',
            description: 'Select Deployment for : Existing or New Tag',
            name: 'GitTagOption',
            script: [
                $class: 'GroovyScript',
                script: [
                    script:
                        'return["Use existing git tag", "create new git tag"]'
                ]
            ]
        ],
        [$class: 'CascadeChoiceParameter',
             choiceType: 'PT_SINGLE_SELECT',
             filterLength: 1,
             filterable: true,
             name: 'GitSelection',
             referencedParameters: 'GitTagOption',
             script: [
                 $class: 'GroovyScript',
                 script: [
                     script:
                         ''' if (GitTagOption.equals("Use existing git tag")){
                                def tags = []
                                def command = "git tag -l"
                                def process = command.execute(null, new File('.'))
                                process.in.eachLine { line ->
                                    tags.add(line.trim())
                                }
                                process.waitFor()
                                return tags
                            }
                            else {
                                def command = "git ls-remote --heads https://github.com/Ravi9449/hello-world.git 'release*'";
                                def process = ["ssh-agent", "bash", "-c", command].execute();
                                return process.text.readLines().collect {
                                    it.split()[1].replaceAll('refs/heads/', '').replaceAll('refs/tags/', '')
                                }
                            }
                        '''
                 ]
             ]
        ],

        [$class: 'CascadeChoiceParameter',
            choiceType: 'PT_SINGLE_SELECT',
            name: 'Stage',
            referencedParameters: 'GitSelection',
            script: [
                $class: 'GroovyScript',
                script: [
                    script:
                        ''' if (GitSelection.contains("release")){
                                return["integration", "review", "test", "preprod", "prod"]
                            } else {
                                return["integration", "review", "test", "preprod", "prod"]
                            }
                        '''
                ]
            ]
        ]
    ])
])

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

 