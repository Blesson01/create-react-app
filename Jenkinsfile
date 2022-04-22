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
    ssh root@107.21.176.248:/root/${JOB_NAME}
   /usr/bin/npm  install
  
  '''
  }
  }
    stage ('Test') {
      steps {
  sh '''
ssh  root@107.21.176.248:/root/
    cd ${JOB_NAME}
  /usr/bin/npm run test
  '''
      }
    }
        stage ('Run') {
      steps {
        
        sh '''
       ssh root@107.21.176.248:/root/
    cd ${JOB_NAME}
        /usr/bin/npm run start
        '''
}
    }
    
  }

}
