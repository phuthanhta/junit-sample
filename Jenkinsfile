pipeline {
    agent any
	tools { 
        maven 'maven3.3.9' 
        jdk 'java1.8.0_144' 
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                //sh "${maven}/bin/mvn test"
		bat "mvn test"
            }
        }
    }
	post {
		always {
		   echo 'Always'
		   echo "Post-Init result: ${currentBuild.result}"
                   echo "Post-Init currentResult: ${currentBuild.currentResult}"
		   echo "Get Current Result: ${currentBuild.getCurrentResult()}"
		 //submitJUnitTestResultsToqTest([apiKey: '6a54dd8d-8f8a-4ac4-9673-6d05c2e5712f', containerID: 12524, containerType: 'TEST-CYCLE', createNewTestRunsEveryBuildDate: true, createTestCaseForEachJUnitTestClass: true, environmentID: 0, overwriteExistingTestSteps: false, parseTestResultsFromTestingTools: true, parseTestResultsPattern: 'target/**/**.xml', projectID: 3964, qtestURL: 'https://sandbox.qtestdev.com', submitToExistingContainer: true])
		   submitJUnitTestResultsToqTest([apiKey: '6a54dd8d-8f8a-4ac4-9673-6d05c2e5712f', containerID: 6215, containerType: 'RELEASE', createNewTestRunsEveryBuildDate: false, createTestCaseForEachJUnitTestClass: false, environmentID: 484, overwriteExistingTestSteps: false, parseTestResultsFromTestingTools: true, parseTestResultsPattern: 'target/**/**.xml', projectID: 233, qtestURL: 'https://sandbox.qtestdev.com', submitToExistingContainer: true])


		}
		success {
			echo 'Success'
		}
		failure {
			echo 'Failure'
		}
	}    
}
