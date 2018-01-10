node('Exacnode'){
   stage('Preparation') {

	git url: 'https://github.com/LearnShareKnowledge/demo_1.git', branch: 'master' 
   }
   
   stage('Build') {
   	sh 'chmod 755 LearnShareKnowledgeDemoProject/gradlew;cd LearnShareKnowledgeDemoProject/;./gradlew clean build'       
   }
   
   stage('Send code to Sonar') {
   def sonarqubeScannerHome = tool 'SonarQubeScanner';
   
   }

}
