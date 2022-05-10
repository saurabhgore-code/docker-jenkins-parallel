pipeline {
	agent any
    environment {
		DOCKERHUB_CREDENTIALS=credentials('deploy')
	}
    stages
	{	
	stage('clone the repo')
		{ 
	parallel {
		stage('build image')
		{
			steps{	
	 sh 'git clone https://github.com/saurabhgore-code/47billion.git'
			}
		}
	{
        steps{ 
            sh 'docker build -t mysql-image .'
        }
        }
        stage('run nginx image')

        {
        steps{
            sh 'docker run -dt mysql'
        }
        }
}
}
}
}
