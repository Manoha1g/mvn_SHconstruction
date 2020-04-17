@Library('shared-library-ci@master')_

pipeline{
	agent any
    	tools { 
        	maven 'maven-3.6.1' 
	 }
	environment {
		name = "test-env-name"
//		commitId = gitCommitId()
	}
	stages{
//	Checking out the source code....
		stage('scm checkout'){
			steps{
				script {
					echo "checking out from Git ......"
			//		checkout-stage(
			//			branch: "master",
			//			url: "https://github.com/Manoha1g/mvn_SHconstruction.git"
			//		)
					checkout-stage()
					echo "Checkout completed ...."
				}
			}
		}
//	Maven artifact build stage
		stage('maven build'){
			steps{
				sh 'mvn clean install'
			}
		}
		stage('test'){
			steps{
				echo "Please find the below worspace path:"
				echo "${workspace}"
				echo "${name}"
			//	environment {
			//		name = 'test-stage-name'
			//		author = "test-author"
			//		echo "${name}"
			//		echo "${author}"
			//	}
			}
		}
		stage('set Build Number'){
			steps{
				script{
					currentBuild.displayName = "#--hello-world-"+currentBuild.number
				}
//				echo ${commitId}
			}
		}
	}
}
def gitCommitId(){
	def latestCommitId = sh script: '''git rev-parse --short HEAD''', returnStdio: true
	return latestCommitId
}
