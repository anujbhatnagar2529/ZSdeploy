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
                 stage('StagingServer') {
                 steps {
                    echo('Welcome to StagingServer')
                 }
                 }
				stage('Staging Server2') {
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
                 stage('DeployedServer') {
                 parallel { 
							stage('Staging Server2') {
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
							stage('Staging Server2') {
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
