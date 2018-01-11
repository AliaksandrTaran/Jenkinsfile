node('Exacnode'){ 
   def scannerHome = tool 'SonarQubeScanner'
   stage('Preparation') {

	git url: 'https://github.com/AliaksandrTaran/demo_1.git', branch: 'master' 
   }
   
   stage('Build') {
   	sh 'chmod 755 LearnShareKnowledgeDemoProject/gradlew;cd LearnShareKnowledgeDemoProject/;./gradlew clean build'       
   }
   
   stage('Signing project'){
        signAndroidApks (
        keyStoreId: "JenkKeyStore",
        keyAlias: "andrs",
        apksToSign: "**/*-unsigned.apk"
	)
	
   }
   
   stage('Send code to Sonar') {
      sh "${scannerHome}/bin/sonar-scanner -Dsonar.login=sonar -Dsonar.password=sonar -Dsonar.sources=. -Dsonar.projectVersion=1.0 -Dsonar.projectKey=my_project -Dsonar.projectName=my_project -Dsonar.jdbc.username=sonar -Dsonar.jdbc.password=sonar" 
   }
   stage('Upload to Nexus'){
      sh "for file in `ls ${workspace}/SignApksBuilder-out/zipalign/`;do curl -v --user nexus:nexus -T \"${workspace}/SignApksBuilder-out/zipalign/$file\" \"http://10.6.211.142:8081/repository/mob-app/$file\"; done"
   }
   stage('Last Step'){
   sh "echo Success"
   }
}
