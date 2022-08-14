pipeline {
    agent any 
    stages {
       stage('Git Checkout') {
            steps {
               gitCheckout(
                  branch: "master",
                  url: "https://github.com/bala3404/sample-web-application.git"
                )
            }
       }	        
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
