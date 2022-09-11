pipeline{
   agent any
   stages{
      stage('Build Application'){
      	  steps{
      	  	 bat 'mvn clean install'
      	  
      	  }
      }
      
      stage('Deploy Cloud'){
      	environment{
      	  ANYPOINT_CREDENTIALS = credentials('anypointPlatform')
      	
      	}
      	
      	steps{
      		echo 'Deploying only because of code commit...'
        	echo 'Deploying to  sand environent....'
        	bat 'mvn package deploy -DmuleDeploy -Dusername=${ANYPOINT_CREDENTIALS_USR} -Dpassword=${ANYPOINT_CREDENTIALS_PSW} -DworkerType=Micro -Dworkers=1 -Dregion=us-west-2'
      	
      	}
      
      
      }
   
   
   }




}