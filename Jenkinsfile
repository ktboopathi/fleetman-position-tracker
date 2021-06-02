node {
 stage('Preparation') {
	git 'https://github.com/ktboopathi/fleetman-position-tracker'
 }
 stage('Build') {
	sh 'mvn package'
 }
 stage('Results') {
	//junit '**/target/surefire-reports/TEST.*.xml'
	//archive 'target/*.jar'
 }
}
