node {
 stage('Preparation') {
	git 'https://github.com/ktboopathi/fleetman-position-tracker'
 }
 stage('Build') {
	sh 'mvn package'
 }
 stage('Results') {
	junit '**/target/surefire-reports/TEST.*.xml'
	archive 'target/*.jar'
 }
 stage('Deploy') {      
	withCredentials([aws(accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'awscredentials', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY')]) {
           ansiblePlaybook credentialsId: 'SSH', installation: 'ansible', playbook: 'deploy.yaml', sudoUser: null
     }
}
