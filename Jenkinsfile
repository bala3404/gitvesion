pipeline {
    agent any 
    stages {     
      stage('branch name') {
           steps {
             
               echo "${env.BRANCH_NAME}"
			  
			   sh '''
			     printenv
			     gitversion
				  
		         	 '''	
                 }
               }
	    }
     
	   } 
