pipeline {
    agent any

    tools {
        maven "MAVEN"
        jdk "JDK"
    }

    stages {
        stage('Initialize'){
            steps{
                echo "PATH = ${M2_HOME}/bin:${PATH}"
                echo "M2_HOME = /opt/maven"
            }
        }
        stage('Build1') {
            steps {
                dir("/var/lib/jenkins/workspace/new") {
                sh 'mvn -B -DskipTests clean package'
                }
            
            }
        stage('Build2') {
            steps {
                echo "hello world"
                }
            
            }
            
        }
        
     }
    post {
       always {
          junit(
        allowEmptyResults: true,
        testResults: '*/test-reports/.xml'
      )
      }
   } 
}
