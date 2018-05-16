pipeline {
agent any
stages {
      stage ('compile stage'){
	
	steps {
	    withMaven(Maven : 'maven_3_5_0') {
		      sh 'mvn clean compile'
         }
		}
       }		
      stage ('Testing stage'){
	   
	   steps {
	    withMaven(Maven : 'maven_3_5_0') {
		      sh 'mvn test'
		}
       }
	   }
	   
	   stage ('Deployment stage'){
	   
	   steps {
	    withMaven(Maven : 'maven_3_5_0') {
		      sh 'mvn Deploy'
		}
        }
        }
      }
    } 