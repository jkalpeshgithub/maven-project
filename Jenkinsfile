pipeline {
    agent any
    stages {
        stage ('SCM Checkout') {
            steps {	
			git credentialsId: '62606cb8-c80d-41d6-b9ee-f8c241074775', url: 'https://github.com/jkalpeshgithub/maven-project.git'
		    }
        }

        stage ('Code Test') {
			steps{
			withMaven(maven: 'LocalMaven') 
		      {
		     sh 'mvn test'
		      }
	       }	
	
        }
		
		
        stage ('deploy to tomcat'){

			steps {
			sshagent (['172.31.16.177']) {
			sh 'scp -o StrictHostKeyChecking=no */target/*.war  ec2-user@172.31.16.177:/var/lib/tomcat/webapps'
					}
					}
		}

}
}
 
