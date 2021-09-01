pipeline {
    environment { 
   	NAME = "ramesh"
   	IMAGE = "${NAME}:${VERSION}"
	NUMBER = "${NAME}:${BUILD_NUMBER}"
	VERSION = "${BUILD_NUMBER}"
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
			 sh 'sudo docker build -t ${NUMBER} .'
		   }		
            }
	    stage('deploy') {
		   steps {
			   sh 'VERS = "${VERSION}-1"'
			   sh 'echo ${VERS}'
			   sh 'sudo docker run -dti --name ${NAME}-${BUILD_NUMBER} -p ${BUILD_NUMBER}:80 ${NUMBER}'
		   }		
            }
        }
    }
	
