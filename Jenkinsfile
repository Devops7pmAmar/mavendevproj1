pipeline
{
agent { label 'slave1'}
stages{
stage('download'){
steps{
git credentialsId: 'ddea26d1-8ba1-4472-b2f1-8eba02a01ead', url: 'https://github.com/Devops7pmAmar/mavendevproj1.git'
	}
	}
	stage('build'){
	    steps{
	        sh 'mvn package'
	    }
	}
	stage('sonar'){
	    steps{
	       withSonarQubeEnv('sonarqube') {
    sh "mvn sonar:sonar"
}
	    }
		
	}
	stage('nexus'){
	    steps{
	        sh 'mvn deploy'
	    }
	}
}}
