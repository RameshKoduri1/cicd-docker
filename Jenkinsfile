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
				   //echo "cloning code"
				   //git branch: 'main',
				   git branch -r | awk \'{print $1}\’ ORS=\’\\n\’ > branches.txt’
				   sh ”’cut -d ‘/’ -f 2 branches.txt > branch.txt”’
			      		credentialsId: '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', 
                             		url: 'https://github.com/RameshKoduri1/cicd-docker.git'   
				  // sh ‘git branch -r | awk \'{print $1}\’ ORS=\’\\n\’ >branches.txt’
				   sh "ls -lat"
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
	
