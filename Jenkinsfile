node {
	

	stage('Clone repository') {
		checkout scm
	}

	stage('Build image') {
		app = docker.build("projectdemo")
	}

	stage('Deploy') {
		sh ("docker run -d -p 81:8080 -v /var/log/:/var/log/ projectdemo")
	}
	
	stage('Remove old images') {
		// remove docker pld images
		sh("docker rmi projectdemo:latest -f")
   }
}
