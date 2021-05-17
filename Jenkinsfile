pipeline {
  agent {
      label 'Winrdows_node'
  }
  stages {
     stage('compile') {
        steps {
                echo "Compiled successfully";
                git credentialsId: 'a131e4a7-538e-42c5-a14b-075be1584fbd', url: 'https://github.com/rkdubey720/tomcat_war.git'
        }
     }   
     stage('JUnit') {
         steps {
		echo "JUnit passed Successfully";
		bat 'set JAVA_HOME=C:\\Program Files\\Java\\jdk1.8.0_291\\'
		bat 'echo %JAVA_HOME%'
		bat 'echo %M2_HOME%'
		bat 'mvn package'
         }
     } 
     stage('Quality-test') {
         steps {
		echo "Quality-Test passed Succesfully";
         }
     }
     stage("Deploy") {
  	 steps {
 		echo "Deploy passed successfully";
 	 }
     }
  }
  post {
     always {
	echo "This will always run"
     }
      success {
	echo "This will only run when success"
     }
	  failure {
         echo "This will only run when there is failure"
     }
	  unstable {
	   echo "This will only run when the run marked unstable"
     }
	  changed {
		echo "this will only run if previously failing"
     }
  }

}
    
