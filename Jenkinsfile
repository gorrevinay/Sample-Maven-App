pipeline {
    agent any

    stages {
        stage('SCM Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/gorrevinay/Sample-Maven-App.git']]])
            }
        }
        stage('Build') {
            steps {
                withMaven(maven : 'Maven') {
                    sh "mvn clean install package"
                }
            }
        
        stage('Status'){
            steps{
                echo " Build is success"
            }
        }
    }  
}
