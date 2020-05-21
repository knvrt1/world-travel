pipeline {
   agent any

   stages {
      stage('Hello') {
         steps {
            echo 'Hello World'
            echo 'This is for Biren Query'
         }
      }
      stage('Maven Build') {
         steps {
            withMaven(maven: 'mvn_3.6.3') {
                sh 'mvn clean package'
            }
            archiveArtifacts 'target/devops.war'
         }
      }
      stage('Shell Script') {
         steps {
            sh label: '', script: '''
               #!/bin/bash
               date
               pwd
               echo ${GIT_BRANCH}
               echo ${WORKSPACE}
               echo ${BUILDNUMBER}'''
         }
      }
   }
}
