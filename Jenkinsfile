pipeline {

  agent any
  stages {
        stage('Checkout') {
            steps {
				checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/vchinchambekar/jenkinspull']]])
            }
        }
        stage('Build Code and Image') {
            steps {
                echo '\n=== Building Code ==='
                
            }
        }
	}
}
