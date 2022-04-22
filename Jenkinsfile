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
rsync -avzP ~/workspace/${JOB_NAME}/* root@107.21.176.248:/root/${JOB_NAME}/
    ssh root@107.21.176.248 'cd /root/reactjs-2 && /usr/bin/npm  install'
  
  ssh root@107.21.176.248 'pwd'
  '''
  }
  }
    stage ('Test') {
      steps {
  sh '''
  
ssh  root@107.21.176.248 'cd /root/reactjs-2 && /usr/bin/npm run test'
     
  ssh root@107.21.176.248 'pwd'
  '''
      }
    }
        stage ('Run') {
      steps {
        
        sh '''
       ssh root@107.21.176.248 'cd /root/reactjs-2 && /usr/bin/npm run start'
  
        
         ssh root@107.21.176.248 'pwd'
        '''
}
    }
    
  }

}
