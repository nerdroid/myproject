node {
	

	stage('Clone repository') {
		checkout scm
	}

	stage('Build image') {
		app = docker.build("projectdemo")
	}

	stage('Deploy') {
		sh ("docker run -d -p 8081:80 -v /var/log/:/var/log/ projectdemo")
	}
	
	stage('Remove old images') {
		// remove docker pld images
		sh("docker rmi projectdemo:latest -f")
   }
}
