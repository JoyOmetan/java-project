properties([pipelineTriggers([githubPush()])])

node('linux') {   
	stage('Test') {    
		git 'https://github.com/JoyOmetan/java-project.git'
		sh 'ant -buildfile test.xml'   
	}   
}
