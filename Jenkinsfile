node('Exacnode'){

   def grdHome = tool 'gradle 2.2'
   def javaHome = tool 'java8'
   
   stage('Preparation') {

      	checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/LearnShareKnowledge/demo_1.git']]])     
   }
   
   stage('Build') {
          
   }
   
   stage('Results') {
   
   }

}
