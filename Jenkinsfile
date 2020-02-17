pipeline {
         agent any
         stages {
		stage('Environment') {
			agent { 
				label 'master'
			}
			steps {
				echo "NODE_NAME = ${env.NODE_NAME}"
				sh 'printenv'
			}
		 }


                 stage('DeployedServer') {
                 parallel { 
				stage('Client A') {
				agent {
					//node 'ZSstage2'
					label 'ZScustomer'
				}
				steps {
					echo "NODE_NAME = ${env.NODE_NAME}"
					sh 'hostname -i'

					sh 'echo "Process Started"'
					sh 'pwd'
					
					// User provided input to change the URL of deployed app
					sh 'accessURL.sh anuj'
					
				}
				}
				stage('Client B') {
				agent {
					//node 'ZSstage2'
					label 'ZScustomer'
				}
				steps {
					echo "NODE_NAME = ${env.NODE_NAME}"
					sh 'hostname -i'

					sh 'echo "Process Started"'
					sh 'pwd'

					// User provided input to change the URL of deployed app
					sh 'accessURL.sh anuj'
					
				}
				}
				stage('Client C') {
				agent {
					//node 'ZSstage2'
					label 'ZScustomer'
				}
				steps {
					echo "NODE_NAME = ${env.NODE_NAME}"
					sh 'hostname -i'

					sh 'echo "Process Started"'
					sh 'pwd'
					
					// User provided input to change the URL of deployed app
					sh 'accessURL.sh anuj'
				}
				}
				stage('Client D') {
				agent {
					//node 'ZSstage2'
					label 'ZScustomer'
				}
				steps {
					echo "NODE_NAME = ${env.NODE_NAME}"
					sh 'hostname -i'

					sh 'echo "Process Started"'
					sh 'pwd'
					
					// User provided input to change the URL of deployed app
					sh 'accessURL.sh anuj'
				}
				}
			}
		}
        }
}
