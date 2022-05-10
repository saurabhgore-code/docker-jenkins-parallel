pipeline {
	agent any
    environment {
		DOCKERHUB_CREDENTIALS=credentials('deploy')
	}
    stages
	{	
	stage('clone the repo')
parallel  {
		{
			steps{	
	 sh 'git clone https://github.com/saurabhgore-code/47billion.git'
			}
		}
}
        stage('build image')
parallel {
        {
        steps{ 
            sh 'docker build -t mysql-image .'
        }
        }
}
        stage('run nginx image')
parallel {
        {
        steps{
            sh 'docker run -dt mysql'
        }
        }
        }
}
}
