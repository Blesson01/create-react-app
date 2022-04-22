pipeline{
agent any 
  stages {
    stage ('Source code') {
      tests {
      git branch: 'main', changelog: false, credentialsId: 'f7912342-df96-46fd-b906-32163eb897bf', poll: false, url: 'https://github.com/Blesson01/create-react-app.git'
      }
    }
  
  stage ('Npm install') {
      tests {
    sh 'npm install'
  }
  }
    stage ('Test') {
      tests {
  sh 'npm run test'
      }
    }
        stage ('Run') {
      tests {
        
        sh 'npm run start'
}
    }
    
  }

}
