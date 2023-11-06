pipeline {
	agent any
	
	triggers {
  pollSCM '* * * * *'
}
	parameters {
		choice(name: 'ENVIRONMENT', choices: ['QA','UAT'], description: 'Pick Environment value')
	}
	stages {
	    stage('Checkout') {
	        steps {
			checkout scm			       
		      }}
		stage('Build') {
	           steps {
			  sh '/home/kunal/Documents/devopssoftware/tar/apache-maven-3.9.5/bin/mvn install'
	                 }}
		stage('Deployment'){
		   steps {
		sh 'cp target/CICD.war /home/kunal/Documents/devopssoftware/tar/apache-tomcat-9.0.82/webapps'
			}}	
}}
