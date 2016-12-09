#!groovy

node {
	stage('SCM Checkout') {
		checkout scm
	}
	stage('Environment Setup') {
		env.JAVA_HOME="${tool 'jdk-8u112'}"
	}
	stage('Build') {
		sh "./gradlew clean build"
	}
	stage('Test Report') {
		junit "build/**/TEST-*.xml"
	}
}
