pipeline {
    agent any 
    stages {
      stage('branch name') {
           steps {
             
               echo "${env.BRANCH_NAME}"
			  
			   sh '''
			     printenv
				  
				 '''	
          }
        }
	 }
     stage('main'){
	       when {
		        branch "main"
		   }
           steps {
             
               echo "${env.BRANCH_NAME}"
			   echo "${BRANCH_NAME}"
			   sh '''
			     printenv
				 gitversion /output buildserver
				  
				 '''
				echo "This is main branch Execution"
				script {
				def props = readProperties file: 'gitversion.properties'
                                env.GitVersion_SemVer = props.GitVersion_SemVer
                                env.GitVersion_BranchName = props.GitVersion_BranchName
                                env.GitVersion_AssemblySemVer = props.GitVersion_AssemblySemVer
                                env.GitVersion_MajorMinorPatch = props.GitVersion_MajorMinorPatch
                                env.GitVersion_Sha = props.GitVersion_Sha
				echo env.GitVersion_SemVer
				echo env.GitVersion_MajorMinorPatch
				echo env.Gitversion_FullSemVer
          }
        
	  }
	 } 
      stage('Feature') {
	      when {
		        branch "feature/*"
		  }
          steps {
             
              echo "${env.BRANCH_NAME}"
			   echo "${BRANCH_NAME}"
			   sh '''
			     printenv
				 gitversion /output buildserver
				  
				 '''
				echo "This is master branch Execution"
				script {
				def props = readProperties file: 'gitversion.properties'
                                env.GitVersion_SemVer = props.GitVersion_SemVer
                                env.GitVersion_BranchName = props.GitVersion_BranchName
                                env.GitVersion_AssemblySemVer = props.GitVersion_AssemblySemVer
                                env.GitVersion_MajorMinorPatch = props.GitVersion_MajorMinorPatch
                                env.GitVersion_Sha = props.GitVersion_Sha
				echo env.GitVersion_SemVer
				echo env.GitVersion_MajorMinorPatch
				echo env.Gitversion_FullSemVer
                            }
        
	             }
	      }	  
	}
