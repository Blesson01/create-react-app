pipeline{
agent any 
  stages {
    stage ('Source code') {
      steps {
 git branch: 'main', changelog: false, credentialsId: 'f7912342-df96-46fd-b906-32163eb897bf', poll: false, url: 'https://github.com/Blesson01/create-react-app.git'
     
    
     }
    }
  
  stage ('Npm install') {
      steps {
    sh '''
    
   npm  install
  
  '''
  }
  }
    stage ('Test') {
      steps {
  sh '''
  npm run test
  '''
      }
    }
        stage ('Run') {
      steps {
        
        sh '''
        npm run build
        '''
}
    }
    
  }

}
