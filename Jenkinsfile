node {
  def app 
  stage('clonar') {
    checkout scm  
  }
  stage('construir'){
    app = docker.build("alysondrg19/dockerwebapp")
  }
  stage('insertar'){
    docker.withRegistry('https://registry.hub.docker.com', 'dockerHub') {            
      app.push("${env.BUILD_NUMBER}")            
      app.push("latest")   
    }
  }
}
