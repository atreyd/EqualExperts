pipeline {
	stages{
		stage ('Initialize Maven') {
		    agent any
				tools { 
					maven 'Maven 3.3.9' 
					jdk 'jdk8' 
					}
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                ''' 
            }
        }
		stage('Clone repository') {
			/* Let's make sure we have the repository cloned to our workspace */
				checkout scm
		}
	    stage ('Build JAR') {
            steps {
                echo 'This is a minimal pipeline.'
				sh 'mvn -B -DskipTests clean install'
					
            }
        }
	}
}
