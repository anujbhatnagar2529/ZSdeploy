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
							stage('Customer Server1') {
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
							stage('Customer Server2') {
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
							stage('Customer Server3') {
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
							stage('Customer Server4') {
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
