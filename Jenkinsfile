pipeline {
    agent {label 'slave6' }
    stages {
        stage('checkout') {
            steps {
              sh 'rm -rf weather-update'
            sh 'git clone https://github.com/Ranjiniumesh/weather-update.git'
            }
        }
        stage ('build') {
            steps {
                sh 'mvn --version'
                sh 'mvn clean install'
            }
        }
        
        stage ('deploy') {
               steps {
                   sh 'scp /home/slave6/workspace/weather_Develop/target/weather-forecast-app-1.0-SNAPSHOT.jar root@172.31.2.53:/opt/apache-tomcat-9.0.85/webapps'
}
}
    }
}
