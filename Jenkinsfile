properties([pipelineTriggers([githubPush()])])

node('linux') {   
	stage('Test') {    
		git 'https://github.com/JoyOmetan/java-project.git'
		sh 'ant -buildfile test.xml'
		junit 'reports/result.xml'
	}
	stage('Build') {    
		sh 'ant -f build.xml -v'   
	}
	stage ('Deploy'){    
		sh 'aws s3 cp /workspace/java-pipeline/dist/rectangle-4.jar s3://seis665ass11jenkins/' 
	}
}
