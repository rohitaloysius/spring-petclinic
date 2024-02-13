pipeline {
    agent any
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
	stage ('archiving artifacts') {
steps {
archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
}
}
stage ('junit test results'){
steps {
junit stdioRetention: '', testResults: 'target/surefire-reports/*.xml'
}
}
    }
}