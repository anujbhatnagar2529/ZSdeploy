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

					sh 'echo "Build Started"'
					sh 'pwd'
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

					sh 'echo "Build Started"'
					sh 'pwd'
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

					sh 'echo "Build Started"'
					sh 'pwd'
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

					sh 'echo "Build Started"'
					sh 'pwd'
				}
				}
			}
		}
        }
}
