node {
	  // Mark the code checkout 'stage'....	  
	stage 'Stage Checkout'
	
	  // Checkout code from repository and update any submodules	  
	checkout scm
	  sh 'git submodule update --init'  
	
	  stage 'Stage Build'

                    sh './gradlew --console=plain --no-daemon --info --stacktrace'
		//sh "./gradlew"

	  //branch name from Jenkins environment variables
	  echo "My branch is: ${env.BRANCH_NAME}"
	if ${env.BRANCH_NAME} = "Master"
		echo "My build number is 4.0.0"
	elseif ${env.BRANCH_NAME} = "feature"
		echo "My build number is 0.4.0"
	else
		echo "My build number is 0.0.4"
	endif
	
	
	log.info (response.comp.type[3] == "value1" ? "value1 is present" : "value1 is not present")
	env.BRANCH_NAME 
	
	  //build your gradle flavor, passes the current build number as a parameter to gradle
//	  sh "./gradlew"
	
	stage 'test'
    sh 'make test'

    stage 'publish'
    sh 'make publish'
}
