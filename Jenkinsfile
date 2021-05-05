node {
 	properties([parameters([choice(choices: ['service1', 'service2'], description: '', name: 'Choises')])])
 	if (Choises.equals("service1")){
 	checkout scm
 	docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
 	def dockerfile = '/var/lib/jenkins/workspace/Docker-pipeline/service1/Dockerfile .'
 	def customImage = docker.build("qwerty0901/para-v1:${env.BUILD_ID}", "-f ${dockerfile}")
 	 
 	/* Push the container to the custom Registry */
 	customImage.push()
 	}
 	}
 	else if (Choises.equals("service2")){
 	checkout scm
 	docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
 	def dockerfile = '/var/lib/jenkins/workspace/Docker-pipeline/service2/Dockerfile .'
 	def customImage = docker.build("qwerty0901/para-v2:${env.BUILD_ID}", "-f ${dockerfile}")
 	 
 	/* Push the container to the custom Registry */
 	customImage.push()
 	}
 	}
 	}
