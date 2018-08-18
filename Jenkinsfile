pipeline {
        agent any
		tools {
			maven 'Maven For Jenkins'
			jdk 'JDK8'
		}
	stages{
               stage ('Initialize Maven') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                '''
            }
        }
                stage('Clone repository') {
                        /* Let's make sure we have the repository cloned to our workspace */
						steps{
                                checkout scm
							}
				}
            stage ('Build JAR') {
            steps {
                echo 'This is a minimal pipeline.'
                                sh 'mvn -B -DskipTests clean install'

            }
        }
        }
} 
