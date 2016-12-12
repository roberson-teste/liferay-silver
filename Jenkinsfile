#!groovy

node {
	/*stage('Info') {
		echo 'starting awesome pipeline'
	    sh 'env > env.txt'
		sh 'cat env.txt'
	}*/
	stage('SCM Checkout') {
		checkout scm
	}
	stage('Environment Setup') {
		//env.JAVA_HOME="${tool 'jdk-8u112'}"
		bat "gradlew.bat clean"
	}
	stage('Build') {
		bat "gradlew.bat build -x test"
	}
    stage('Test') {
        try {
            bat "gradlew.bat test"
        } finally {
            junit "build/**/TEST-*.xml"
        }
    }
}
