pipeline{
        agent any
	parameters {
  		choice choices: ['DEV', 'QA ', 'UAT'], name: 'ENVIRONMENT'
	}
	triggers {
	  pollSCM '* * * * *'
	}
        stages{
                stage(checkout){
                        steps{
                        git 'https://github.com/mitali-08/pipelineProject.git'
                        }
                }
                stage(compileandbuild){
                        steps{
                        sh 'mvn install'
                        }
                }
                stage(deploy){
                        steps{
                        sh 'cp target/pipelineProject.war /home/mitali/Documents/devops/apache-tomcat-9.0.93/webapps'
                        }
                }
        }
}

