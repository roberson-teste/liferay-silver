#!groovy

node {
	
	stage('Checkout') {
		checkout scm
	}

	stage('Setup') {
		bat 'gradlew.bat clean'
	}

	stage('Build') {
		bat 'gradlew.bat build -x test'
	}

	stage('Test') {
		try {
			bat 'gradlew.bat test'
		} finally {
			junit 'build/**/TEST-*.xml'
		}
	}

}

