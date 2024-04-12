pipeline {
    agent none

    stages {
        stage('Build and run') {
          parallel {
            stage('master-agent-pipeline') {
              agent any {label 'master'}
              stages{
                stage('Build') {
                steps {
                  echo 'Building..'
                  }
                }
      }
              }              
             }
            }
           }
          }
