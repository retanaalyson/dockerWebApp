node {
  def app 
  stage('clone repository') {
    checkout scm  
  }
  stage('Build docker Image'){
    app = docker.build("alysondrg19/dockerwebapp")
  }
  stage('Push Image'){
    docker.withRegistry('https://registry.hub.docker.com', 'dockerHub') {            
      app.push("${env.BUILD_NUMBER}")            
      app.push("latest")   
    }
  }
}
