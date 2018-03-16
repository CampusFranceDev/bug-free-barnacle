#!/bin/env groovy

pipeline {
  agent none
  stages {
    stage('Build') {
      agent {
        docker {
          image 'maven:3.5.0'
        }
      }
      steps {
          sh 'mvn clean install -PbuildDocker'
      }
    }
    
    stage('Build container') {
      agent any
      steps {
        script {
            sh "docker-compose up"
        }
      }
    }
}
