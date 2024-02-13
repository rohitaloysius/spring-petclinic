pipeline {
    agent any
    triggers { pollSCM('*/2 * * * *') }
    stages {
        stage('Git') {
            steps {
                git branch: 'main', url: 'https://github.com/rohitaloysius/spring-petclinic.git'
            }
        }
	stage('Building the code') {
		steps {
		sh 'mvn package'
		}	
	}
stage ('junit test results'){
steps {
junit stdioRetention: '', testResults: 'target/surefire-reports/*.xml'
}
}
    }
}