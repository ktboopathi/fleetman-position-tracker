node {
 stage('Preparation') {
	git 'https://github.com/ktboopathi/fleetman-position-tracker/'
 }
 stage('Build') {
	sh 'mvn package'
 }
 stage('Results') {
	junit '**/target/sunfire-reports/TEST.*.xml'
	archive '/target/*.jar'
 }
} 
