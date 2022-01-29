
pipeline{
    tools{
        jdk 'myjava'
        maven 'mymaven'
    }
	agent any
      stages{
           stage('Checkout'){
	    
               steps{
		             echo 'cloning repository'
                 git 'https://github.com/Nikhil-V-maker/devops_edureka4.git'
              }
          }
          stage('Compile'){
             
              steps{
                  echo 'compile stage'
                  sh 'mvn compile'
	      }
          }
          stage('Code Review'){
		  
              steps{
		    
		              echo 'codeReview stage'
                  sh 'mvn pmd:pmd'
              }
          }
           stage('UnitTest'){
		  
              steps{
	                echo 'Unit Test stage'
                  sh 'mvn test'
              }
               post {
               success {
                   junit 'target/surefire-reports/*.xml'
               }
           }	
          }
          stage('Package'){
		  
              steps{
		              echo 'Packaging'
                  sh 'mvn package'
              }
          }
	     
          
      }
}
