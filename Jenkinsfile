pipeline {
    agent any

    stages {
        stage('clone') {
            steps {
                git branch: 'main', url: 'https://github.com/udamale/project-1-maven-jenkins-CICD-docker-eks-.git'
            }
        }
        stage('maven') {
            steps {
              dir('webapp') {
                  sh 'mvn package'
                }
            }
        }
      stage('tomcat') {
            steps {
                deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tomcat1', path: '', url: 'http://3.7.69.80:8081/')], contextPath: null, war: '**/*.war'
             }
       }
   }
}
