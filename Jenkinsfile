pipeline {
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
			     credentialsId: 'rameshkoduri13@gmail.com'
			     password: 'Rammi@123456'
                             url: 'https://github.com/RameshKoduri1/cicd-docker.git'   
                           sh "ls -lat"
		    }
	    }
        }
    }
	
