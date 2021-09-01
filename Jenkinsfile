pipeline {
    environment { 
   	NAME = "ramesh"
   	IMAGE = "${NAME}:${VERSION}"
	NUMBER = "${NAME}:${BUILD_NUMBER}"
	VERSION = "${env.BUILD_ID}-${env.GIT_COMMIT}"
	int build_num = "${BUILD_NUMBER}"
	GET_REPO = "https://github.com/RameshKoduri1/cicd-docker.git"
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
			    script {
				   // gitBranchCheckout(GET_REPO, BranchToBuild)
			    }
		    }
	    }
	    stage('build') {
		   steps {
			 sh 'sudo docker build -t ${NUMBER} .'
		   }		
            }
	    stage('deploy') {
		   steps {
			   sh 'echo ${VERSION}'
			   sh 'sudo docker run -dti --name ${NAME}-${BUILD_NUMBER} -p ${BUILD_NUMBER}:80 ${NUMBER}'
		   }		
            }
        }
    }
	
