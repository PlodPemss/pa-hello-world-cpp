properties([
	pipelineTriggers([pollSCM('H/3 * * * *')])
	])

node() {
	cleanWs()
	agent none
	stages {
		stage('Checkout') {
			steps {
				checkout scm
			}
		}
		stage('Build') {
			steps {
				sh "make"
				sh "./main"
			}
		}
		stage('Archivage') {
			steps {
				archiveArtifacts artifacts: 'build/**/*.zip
			}
		}
}
