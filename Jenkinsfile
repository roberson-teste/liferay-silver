#!/usr/bin/env groovy

node {
	checkout scm
	env.JAVA_HOME="${tool 'jdk-8u112'}"
	sh "./gradlew clean build"
	step([$class: "JUnitResultArchiver", testResults: "build/**/TEST-*.xml"])
}
