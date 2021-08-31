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
			     https://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@github.com/RameshKoduri1/cicd-docker.git,
                             url: 'ssh://github.com/RameshKoduri1/cicd-docker.git'   
                           sh "ls -lat"
		    }
	    }
        }
    }
	
