#!groovy

stage name: 'setup'
node {
    // Testing
	sh 'pwd'
	sh 'ls -la'
    git url: 'https://github.com/loverde/jenkinsfile-test'
	sh 'pwd'
	sh 'ls -la'
	sh './gradlew clean build'
}

