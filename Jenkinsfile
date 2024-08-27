pipeline {
	agent any
	parameters {
  choice choices: ['DEV', 'QA', 'UAT'], name: 'ENVIRONMENT'
}
	stages {
	    stage('Checkout') {
	        steps {
			git 'https://github.com/mitali-08/pipelineProject.git'			       
		      }}
		stage('Build') {
	           steps {
			  sh 'mvn install'
	                 }}
		stage('Deployment'){
		    steps {
			script {
			 sh '''if ( "${env.ENVIRONMENT}" == \'QA\' ){
                sh 'cp target/pipelineProject.war /home/mitali/Documents/devops/apache-tomcat-9.0.93/webapps'
                echo "deployment has been done on QA!"
                         }
                        else if ( "${env.ENVIRONMENT}" == \'UAT\' ){
                sh 'cp target/pipelineProject.war /home/mitali/Documents/devops/apache-tomcat-9.0.93/webapps'
                echo "deployment has been done on UAT!"
                        }
                        echo "deployment has been done!"
                        fi'''
			
			}}	
}
}
}
