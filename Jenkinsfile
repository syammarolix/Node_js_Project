node{
  stage('Get Code'){ 
      git branch: 'main', credentialsId: 'c0fce032-e1a5-409b-b729-b4fc46d85f5a', url: 'https://github.com/syammarolix/Node_js_Project.git'
    }

  stage("Build") {
    nodejs(nodeJSInstallationName: 'Node.js') { // Use the name you configured
        sh 'npm i sonar-scanner' 
        sh 'npm i sonar-scanner --save-dev'
        sh 'npm i sonarqube-scanner'
         sh   'npm install'
         sh 'npm audit fix'
       // sh 'npm run build'
                }
    }

   
 
  stage('ExecuteSonarQubeReport') {
      sh ' npm run sonar-project.js'
      sh 'sonar-scanner'
      sh "npm run sonar"
      sh 'npm run sonar-scanner'
     
   } 
}
