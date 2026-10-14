#!groovy
// Check devops properties
properties([disableConcurrentBuilds()])

pipeline {
    agent { 
        label 'built-in'
        
    }
    options {
        buildDiscarder(logRotator(numToKeepStr: '10', artifactNumToKeepStr: '10'))
        timestamps()
    }
    stages {
        stage("First step") {
            steps {
                sh "ssh student@172.16.7.163 'hostname&&pwd&&whoami'"
            }
        }
        stage("Second step") {
            steps {
                sh 'ssh student@172.16.7.163 \'uptime\''
            }
        }
    }
}