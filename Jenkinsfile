pipeline {
	agent any
	stages {
		stage('Checkout SCM') {
			steps {
				git 'https://github.com/Ixceee/lab06'
			}
		}

		stage('OWASP Dependency-Check Vulnerabilities') {
			steps {
				dependencyCheck additionalArguments: '--format HTML --format XML', odcInstallation: 'OWASP Dependency-Check Vulnerabilities'
			}
		}
	}	
	post {
		success {
			dependencyCheckPublisher pattern: 'dependency-check-report.xml'
		}
	}
}