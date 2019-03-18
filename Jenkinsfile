node {
    def nodeHome = tool name: 'node-9.8.0', type: 'jenkins.plugins.nodejs.tools.NodeJSInstallation'
    env.PATH = "${nodeHome}/bin:${env.PATH}"

    stage('check tools') {
        sh "node -v"
        sh "npm -v"
    }

    stage('checkout') {
        checkout scm
    }

    stage('npm install') {
        sh "npm install"
    }
    stage ('npm install angular'){
      sh "npm install -g @angular/cli@latest"
   }
   stage ('run angular project'){
      sh "npm run ng build"
   }
   
   stage('Create artifact') {
        sh "tar czvf dist.tar.gz dist"
    }

}
