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
   }
   stage('custom2') {    
   }
   stage('custom3') {    
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
