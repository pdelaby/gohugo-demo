#!/usr/bin/env groovy

node {
	 
	def commitId
	stage('checkout'){
		// checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'SubmoduleOption', disableSubmodules: false, parentCredentials: false, recursiveSubmodules: true, reference: '', trackingSubmodules: false]], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/pdelaby/...']]])
		cleanWs()
		checkout scm

		// checkout les submodules (le thème)
		sh 'git submodule update --init'
		commitId = sh(returnStdout: true, script: 'git rev-parse HEAD')

		commitId = commitId.trim()
	}

    stage('build docker') {
        docker.build("pdy/hugodemo:${commitId}", '.')
		sh "docker tag pdy/hugodemo:${commitId} pdy/hugodemo:latest"
    }

	stage('stop docker'){
		sh "docker-compose stop"
	}

	stage('start docker'){			
		sh "docker-compose up -d "
	}
}