#!groovy

node {
	
	stage('Checkout') {
		checkout scm
	}

	stage('Setup') {
		bat 'gradlew clean'
	}

	stage('Build') {
		bat 'gradlew build -x test'
	}

	stage('Test') {
		try {
			bat 'gradlew test'
		} finally {
			junit 'build/**/TEST-*.xml'
		}
	}

}

