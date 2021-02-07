pipeline{
	agent any

	stage('Create kubernetes cluster') {
			steps {
				withAWS(region:'us-west-2', credentials:'aws_credentials') {
					sh '''
						./create_EKS.sh
					'''
				}
			}
		}

}
