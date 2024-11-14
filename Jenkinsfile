pipeline {
    agent any
	stages{
	stage('test'){
		  steps{
			sh 'mvn test'
		  }
	}
	 stage('SonarQube') {
                        steps {
                         withSonarQubeEnv('SonarQube') { 
				 
            sh 'mvn clean verify sonar:sonar \
            -Dsonar.projectKey=appproject \
            -Dsonar.host.url=http://43.205.144.92:9000 \
            -Dsonar.login=sqp_c3b7d53cec756ce5628ac8c4e38a514759667406'
            }
          }
        }
          stages{
	    stage('package'){
		  steps{
			sh 'mvn package'
		    }
	    }
        }
    }
}
