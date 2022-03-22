pipeline {
    agent any
    tools {
	 maven 'maven'
    }
	
    stages {
        stage('build') {
            steps{
                 sh script: 'mvn clean package'
            }
        }
	satge('upload war file to nexus'){
	    steps{
                 nexusArtifactUploader artifacts: [
		     [
					
			 artifactId: 'maven-project', 
			 classifier: '', 
			 file: 'target/maven-projec-1.0-SNAPSHOT.war', 
			 type: 'war'
		     ]
				
		  ], 
		  credentialsId: 'nexus-user-credentials', 
	          groupId: 'com.example.maven-project', 
		  nexusUrl: '3.110.223.80:8081', 
		  nexusVersion: 'nexus3', 
		  protocol: 'http', 
		  repository: 'hdfc-snap', 
		  version: '1.0-SNAPSHOT'
			 
            }
        }
    }
}
