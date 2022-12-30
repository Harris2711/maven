pipeline {
  agent any
  tools {
    maven 'maven'
  }
  stages {
   stage ('Initialize') {
            steps {
                sh '''
                    M2_HOME=/opt/maven
                    M2=/opt/maven/bin
                    PATH=$PATH:$HOME/bin/:$JAVA_HOME:$M2:$M2_HOME
                    export PATH
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                    whoami
                '''
            }
        }
    stage('Build app') {
      steps {
        sh 'mvn clean install package'
      }
    }
    stage('Deploy to tomcat') {
      steps {
        sh 'scp -i $tomcat_pem -o "StrictHostKeyChecking=no" webapp/target/webapp.war ubuntu@18.221.178.126:/opt/tomcat/webapps'
      }
}
 post {
      always {
        emailext to: 'mohammedharris556@gmail.com',
        attachLog: true, body: "Dear team pipeline is ${currentBuild.result} please check ${BUILD_URL} or PFA build log", compressLog: false,
        subject: "Jenkins Build Notification: ${JOB_NAME}-Build# ${BUILD_NUMBER} ${currentBuild.result}"
     }
 }
}
}
