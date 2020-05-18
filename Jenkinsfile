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
        sh 'ssh -i /root/foodie.pem ubuntu@34.217.131.87 "rm -rf ~/Images"'
    	sh 'scp -ri /root/foodie.pem Images ubuntu@34.217.131.87:~/Images'
        sh 'ssh -i /root/foodie.pem ubuntu@34.217.131.87 "rm ~/Images/Jenkinsfile && systemctl restart apache2"'


		cleanWs()

	        }


    }

}
}