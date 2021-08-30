pipeline {
    agent any
    stages {
		  stage('Checkout external proj') {
        steps {
            git branch: 'master',
                credentialsId: 'rameshkoduri13@gmail.com',
                url: 'https://github.com/RameshKoduri1/cicd-docker.git'
            sh "ls -lat"
        }
      }        
		  stage('build') {
			  steps {
				  sh 'docker build -t Dockerfile .'
			  }		
      }
    }
}
