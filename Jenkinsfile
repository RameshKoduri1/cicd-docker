pipeline {
    environment { 
   	NAME = "ramesh"
   	VERSION = "${env.BUILD_ID}-${env.GIT_COMMIT}"
   	IMAGE = "${NAME}:${VERSION}"
    }
    agent any
    stages {
	    stage('clean Workspace') {
		    steps {
			    cleanWs()
		    }
	    }
	    stage('clone') {
		    steps {  
                           git branch: 'main',
			     credentialsId: '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',
                             url: 'https://github.com/RameshKoduri1/cicd-docker.git'   
                           sh "ls -lat"
		    }
	    }
	    stage('build') {
		   steps {
			 sh 'sudo docker build -t ${IMAGE} .'
		   }		
            }
        }
    }
	
