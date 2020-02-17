pipeline {
	agent {node {label 'master'} }
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
			agent {node {label 'ZScustomer'} }
			steps {
					echo "NODE_NAME = ${env.NODE_NAME}"
					sh 'hostname -i'
			stage('Integration test') {
			steps {
			echo "Running the integration test..."
			}
			}
		}
	}
}
}
}
