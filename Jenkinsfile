pipeline {
 agent any
  
  environment {
    ENV = "prd"
  }
  
  stages {
    stage('Hello') {
      when {
        environment name:"ENV", value:"dev"
      }
      
      steps {
        echo 'This is dev.'
      }
    }
   
   stage('custom1') {    
    steps {
     echo 'custom stage test1'
    }
   }
   stage('custom2') {      
    steps {
     echo 'custom stage test2'
    }  
   }
   stage('custom3') {      
    steps {
     echo 'custom stage test3'
    }  
   }
    
    stage('Bye') {
      when {
        environment name:"ENV", value:"prd"
      }
      
      steps {
        echo 'This is prd.'
      }
    }
  }
}

node {
 def env = 'dev'
 def sth = 'hello'
 
 if(env == 'dev') {
  sth = 'bye'
 }
 
 stage('Start build') {
  echo "mvn -p $sth"
  print("$sth")
 }
 
 stage('custom stage') {
  echo "hello jenkins"
 }
}
'''
node('docker') {
 checkout scm
 stage('Build') {
  docker.image('node:6.3').inside {
   sh 'npm ?version'
  }
 }
}
'''
