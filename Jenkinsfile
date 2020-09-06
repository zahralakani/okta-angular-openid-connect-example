node {
    def nodeHome = tool name: 'node-9.8.0', type: 'jenkins.plugins.nodejs.tools.NodeJSInstallation'
    env.PATH = "${nodeHome}/bin:${env.PATH}"

    stage('check tools') {
        bat "node -v"
        bat "npm -v"
    }

    stage('checkout') {
        checkout scm
    }

    stage('npm install') {
        bat "npm install"
    }
    stage ('npm install angular'){
      bat "npm install -g @angular/cli@latest"
   }
   stage ('run angular project'){
      bat "npm run ng build"
   }
   
   stage('Create artifact') {
        bat "tar czvf dist.tar.gz dist"
    }

}
