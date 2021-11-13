pipeline {
	agent any
	stages{

		stage('clone and clean repo'){
			steps {
				cleanWs()
				sh "git clone -b master https://github.com/arthking17/MyFirstAngular.git"
			}
		}

		stage('Build')
		{
			steps{
				script{
					sh "ansible-playbook MyFirstAngular/ansible/build.yml -i MyFirstAngular/ansible/inventory/host.yml"
				}
			}
		}
		
		stage('docker')
		{
		  steps{
		    script{
		      sh "ansible-playbook MyFirstAngular/ansible/docker.yml -i MyFirstAngular/ansible/inventory/host.yml"
		    }
		  }
		}

	}
}
