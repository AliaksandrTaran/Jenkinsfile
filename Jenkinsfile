node('Exacnode'){

   
   stage('Preparation') {

      	checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/LearnShareKnowledge/demo_1.git']]])    
	 
   }
   
   stage('Build') {
        sh "gradle clean build"  
   }
   
   stage('Results') {
   
   }

}
