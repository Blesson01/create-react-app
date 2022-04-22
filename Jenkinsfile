pipeline{
agent any 
  stages {
    stage ('Source code') {
      steps {
     sh '''
     ssh root@107.21.176.248 date
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
