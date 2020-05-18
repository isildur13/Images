pipeline {
    agent { label 'foodiebuild' }
    stages {
        stage('checkout') {
            steps {
		cleanWs()
                sh 'git clone git@github.com:isildur13/Images.git'
            }
        }

	stage('deploy'){

		steps {
		sh 'echo ".......Deploying......."'
		sh 'scp -ri /root/foodie.pem Images ubuntu@34.217.131.87:~/Images'
		cleanWs()

	        }


    }

}
}