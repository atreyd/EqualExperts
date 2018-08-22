pipeline {
        agent any
		tools {
			maven 'Maven For Jenkins'
			jdk 'JDK8'
		}
	stages{
        stage('Clone repository') {
                        /* Let's make sure we have the repository cloned to our workspace */
           steps{
                        checkout scm
                }
        }
            stage ('Build WAR') {
            steps {
                echo 'This is the stage to build war'
                 sh 'mvn -B -DskipTests clean install'
            }
        }
            stage ('Copy Artefacts') {
            steps {
                echo 'This is the final stage to copy in /mnt/artefact.'
                 sh 'sudo cp /var/lib/jenkins/workspace/EqualExperts/target/spring-petclinic-2.0.0.BUILD-SNAPSHOT.war /mnt/artefact/.'
            }
        }
        }
} 
