#!groovy

node {

	stage('Info') {
		echo 'starting awesome pipeline'
	    sh 'env > env.txt'
		sh 'cat env.txt'
	}

	stage('SCM Checkout') {
		checkout scm
	}

	stage('Environment Setup') {
		env.JAVA_HOME="${tool 'jdk-8u112'}"
		sh "./gradlew clean"
	}

	stage('Build') {
		sh "./gradlew build -x test"
	}

    stage('Test') {
        try {
            sh "./gradlew test"
        } finally {
            junit "build/**/TEST-*.xml"
        }
    }

}

