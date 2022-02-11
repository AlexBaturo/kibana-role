pipeline {
    agent {
        label "docker"
    } 
    stages {
        stage('Prepare role') { 
            steps {
                    git branch: 'main', credentialsId: 'github', url: 'git@github.com:AlexBaturo/kibana-role.git'
                    sh "pip3 install \"molecule==3.4.0\" molecule_docker"
                    sh "mkdir molecule/default/files"
                    sh 'ls'
            }
        }
        stage('Launch test') { 
            steps {
                    sh 'molecule test'
            }
        }
    }
}