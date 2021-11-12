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
					sh "cd MyFirstAngular/"
					sh "ls > ls_output"
					sh "ansible-playbook MyFirstAngular/ansible/build.yml -i MyFirstAngular/ansible/inventory/host.yml"
				}
			}
		}

	}
}
