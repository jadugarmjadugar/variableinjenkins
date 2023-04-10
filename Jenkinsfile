@Library('test-shared') _ 

pipeline {
  agent any
  parameters {
        choice(name: "javaversion", choices: ["master", "feature", "development"], description: "Sample multi-choice parameter")
        string(name: "wordplay", defaultValue: "testingword", description: "Sample string parameter")
        string(name: "branchname", description: "enter branch name")
    }
  stages{
    stage('Test') {
      steps {
        echo "${params.wordplay}" 
        echo "new variable ${params.branchname}"
        echo "${params.javaversion}"
      }
    }
    stage('Test2') {
      steps {
        sh 'echo "test2"'
      }
    }
    stage('Build') {
      steps {
          hiscript(name:"karan",dayOfWeek:"Thursday")
        }
      }
    stage('new') {
      steps {
          script{
              echo "new"
              hi()
         }
        }
      } 
  }
    post {
        success {
            echo "build success"
        }
        failure {
            echo 'Build failed!'
            sh 'make clean'
        }
    }
      
}    
