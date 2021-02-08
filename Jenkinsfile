pipeline{
	agent any
	stages{
		stage('Lint HTML') {
			// agent { docker { image 'python:3.5.1' } }
			steps {
				sh 'tidy -q -e *.html'
			}
		}

		stage("Build & Push Docker Image to DockerHub"){
			// agent {
			// 	docker {image 'ubuntu'}
			// }
			steps{
				withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: 'dockerhub', usernameVariable: 'DOCKER_USERNAME', passwordVariable: 'DOCKER_PASSWORD']]){
					sh '''
						whoami
						sudo groupadd docker
						sudo usermod -aG docker jenkins
						su -s jenkins
						docker build -t asghostknight/capstone .
					'''
				}
			}
		}

	}

}
