pipeline
{
agent any
  {
	stage "SCM Checkout"{
	  steps {	
			git credentialsId: '62606cb8-c80d-41d6-b9ee-f8c241074775', url: 'https://github.com/jkalpeshgithub/maven-project.git'
		    }
	}
	stage "code test"
	{
	  steps 
		{
			withMaven(maven: 'LocalMaven') 
		{
		  sh 'mvn test'
		}
	}	
	}
}
}
