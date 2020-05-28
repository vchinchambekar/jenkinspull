peline {

  agent any
  environment {
  JF_REGISTRY="dbg-digital-suite-solutions-team-ase-dev-docker-local.artifactory.swg-devops.com"
  
   }
  stages {
        stage('Checkout') {
            steps {
				checkout([$class: 'GitSCM', branches: [[name: '*/feature-microservice']], userRemoteConfigs: [[credentialsId: 'GitHub_Creds', url: 'https://github.ibm.com/disco/UserService.git']]])
            }
        }
        stage('Build Code and Image') {
            steps {
                echo '\n=== Building Code ==='
                sh label: '', script: 'mvn -Dmaven.test.failure.ignore=true install'
				echo '\n=== Building Docker Image ==='
				sh 'docker build -t ${JF_REGISTRY}/ase-userservice:dev-v3-$BUILD_NUMBER-$JOB_NAME .'
				sh 'docker push ${JF_REGISTRY}/ase-userservice:dev-v3'
            }
        }
	}
}
