pipeline{
agent any 
  stages {
    stage ('Source code') {
      steps {
     sh '''
     ssh root@107.21.176.248:/root && /usr/bin/git branch: 'main', changelog: false, credentialsId: 'f7912342-df96-46fd-b906-32163eb897bf', poll: false, url: 'https://github.com/Blesson01/create-react-app.git'
     
     '''
     }
    }
  
  stage ('Npm install') {
      steps {
    sh '''
    
    ssh root@107.21.176.24 && cd /root/create-react-app &&   /usr/bin/npm  install
  
  '''
  }
  }
    stage ('Test') {
      steps {
  sh '''
  ssh root@107.21.176.24 && cd /root/create-react-app &&   /usr/bin/npm run test
  '''
      }
    }
        stage ('Run') {
      steps {
        
        sh '''
        ssh root@107.21.176.24 && cd /root/create-react-app &&   /usr/bin/npm run start
        '''
}
    }
    
  }

}
