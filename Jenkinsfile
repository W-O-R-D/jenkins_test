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
