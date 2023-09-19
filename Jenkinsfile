node{
  stage('Get Code'){ 
      git branch: 'main', credentialsId: 'c0fce032-e1a5-409b-b729-b4fc46d85f5a', url: 'https://github.com/syammarolix/Node_js_Project.git'
    }

  stage("Build")
   {
     nodejs(nodeJSInstallationName: 'npm') {
        sh 'npm install'
        sh 'npm build'
       
      }
   }  
 
  stage('ExecuteSonarQubeReport') {
      sh 'npm run sonar'
   } 
}
