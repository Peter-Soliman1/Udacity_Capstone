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
			agent {
				docker {image 'ubuntu'}
			}
			steps{
				withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: 'dockerhub', usernameVariable: 'USERNAME', passwordVariable: 'USERPASS']]){
					sh '''
						docker build -t asghostknight/capstone .
						docker login -u $USERNAME -p $USERPASS
						docker push asghostknight/capstone
					'''
				}
			}
		}

	}

}
