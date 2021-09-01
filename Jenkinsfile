pipeline {
    environment { 
   	NAME = "ramesh"
   	IMAGE = "${NAME}:${VERSION}"
	NUMBER = "${NAME}:${BUILD_NUMBER}"
	VERSION = "${BUILD_NUMBER}"
	build_num = "${BUILD_NUMBER}"
	pre_build_num = (build_num as int) - 1
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
			   sh 'echo ${pre_build_num}'
			   sh 'sudo docker run -dti --name ${NAME}-${BUILD_NUMBER} -p ${BUILD_NUMBER}:80 ${NUMBER}'
		   }		
            }
        }
    }
	
