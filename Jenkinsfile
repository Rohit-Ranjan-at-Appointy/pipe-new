CHOICES = [];

def app = 'unknown'
pipeline {
  stages {
    stage("build") {
      steps {
        script {
        CHOICES = ['service1', 'service2','service3', 'service4','service5']
        env.Module = input message: 'what are we deploying today',
        parameters:[choice(choices: CHOICES, description: 'select a tag forn this')]
        
        echo "${Module}"
        sh cd "${Module}" 
 	      checkout scm
 	      docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
 	      app = docker.build("qwerty0901/para-v10:${env.Module}", "-f ${dockerfile}")
        app.push()
        }
       }
      }
    }
  }
}
  
