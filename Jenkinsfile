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
			 sh '''if [ $ENVIRONMENT = "QA" ];then
	cp target/GRRAS1.war /home/mitali/Documents/devops/apache-tomcat-9.0.93/webapps
elif  [ $ENVIRONMENT = "UAT" ];then
         cp target/GRRAS1.war /home/mitali/Documents/devops/apache-tomcat-9.0.93/webapps
echo "deployment has been done!"
fi'''
			
			}}	
}
}
}
