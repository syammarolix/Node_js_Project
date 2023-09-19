node {
  stage('Get Code') { 
    git branch: 'main', credentialsId: 'c0fce032-e1a5-409b-b729-b4fc46d85f5a', url: 'https://github.com/syammarolix/Node_js_Project.git'
  }

  stage('Build') {
    nodejs(nodeJSInstallationName: 'Node.js') {
      sh 'npm install'
      sh 'npm audit fix'
      sh 'npm run build'  // You can uncomment this line if your project requires a build step
    }
  }
 
  stage('SonarQube Analysis') {
    sh 'sonar-scanner'
  }
  
  stage('Custom SonarQube Reporting') {
    sh 'node run sonar-project.js'
    sh 'npm run sonar'
    sh 'npm run sonar-scanner'
  }
}
