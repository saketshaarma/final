def CONTRAIL_VERSION="r5.1"
def BRANCH="R5.1"
image_name="tungstenfabric/developer-sandbox"
image_tag="r5.1"
pipeline {
	agent any
	stages {
		stage ("Creating Hash based manifest") {
			steps {
				sh label: '',
				script: "docker exec  contrail-developer-sandbox bash -c \'set -x; cd /root/contrail; repo manifest -r -o /root/contrail-dev-env/manifest_"$(date +"%H:%M-%Y-%m-%d")".xml\'"
			}
	}
	
		stage ("Cloning Bit Bucket Repo") {
			steps {
				def BRANCH='master'
				sh label: '',
				script: 'mkdir -p bitbucket'
				dir ("bitbucket"){
					git 'git@bitbucket.org:atsgen/ats-infra.git'
				}
			}
	}
		
	}
}
