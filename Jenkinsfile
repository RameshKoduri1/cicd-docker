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
			    
                           git branch: 'master',
                             credentialsId: 'rameshkoduri13@gmail.com',
                             url: 'https://github.com/RameshKoduri1/cicd-docker.git'   
                           sh "ls -lat"
		    }
	    }
        }
    }
	
