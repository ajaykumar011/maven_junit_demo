// Powered by Infostretch 

timestamps {

node () {

	stage ('maven-gunit-demo - Checkout') {
 	 checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'git-crendetials', url: 'https://github.com/ajaykumar011/maven_junit_demo.git']]]) 
	}
	stage ('maven-gunit-demo - Build') {
 			// Maven build step
	withMaven(maven: 'M3') { 
 			if(isUnix()) {
 				sh "mvn -f NumberGenerator/pom.xml clean package " 
			} else { 
 				bat "mvn -f NumberGenerator/pom.xml clean package " 
			} 
 		}
		// JUnit Results
		junit 'NumberGenerator/target/surefire-reports/*.xml' 
	}
}
}