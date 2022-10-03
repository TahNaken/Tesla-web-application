pipeline{
	  agent any 
	  tools {
	    maven "Maven3.8.6"
	  }  
	  stages {
	    stage('1GetCode'){
	      steps{
	        sh "echo 'cloning the latest application version' "
	        git 'https://github.com/TahNaken/Tesla-web-application.git'
	      }
  }



stage('3Test+Build'){
	      steps{
	        sh "echo 'running JUnit-test-cases' "
	        sh "echo 'testing must passed to create artifacts ' "
	        sh "mvn clean package"
	      }
	    }
	      
	      
stage('4CodeQuality'){
	      steps{
	        sh "echo ' CodeQualityAnalysis' "
	        sh "mvn sonar:sonar"
	      }	      
}	      
	      
stage('5uploadNexus'){
	      steps{
	        sh "mvn deploy"
	      }
	    }
	  
stage('8deploy2prod'){
      steps{
         deploy adapters: [tomcat9(credentialsId: 'tomcat-credentials', path: '', url: 'http://3.144.188.239:8080/')], contextPath: null, war: 'target/*war'  
    }     
  }
	      
	      
	      
	      
	      
	  }
                
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    












}
