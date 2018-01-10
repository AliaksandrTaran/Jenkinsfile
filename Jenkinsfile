node('Exacnode'){
   def grdHome = tool 'gradle2.2'
   def javaHome = tool 'java8' 
   stage('Preparation') {

	git url: 'https://github.com/LearnShareKnowledge/demo_1.git', branch: 'master' 
   }
   
   stage('Build') {
   	sh 'chmod 755 LearnShareKnowledgeDemoProject/gradlew;cd LearnShareKnowledgeDemoProject/;./gradlew clean build'       
   }
   
   stage('Results') {
   
   }

}
