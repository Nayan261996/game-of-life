pipeline {
    agent { label 'QA' }
    stages('GOL'){
        stage('permission'){
            steps { 
                sh 'sudo su -'
            }
        }
        stage('copy-from-s3'){
            steps { 
                sh 'aws s3 cp s3://velpproj/gameoflife.war /mnt/webserver/apache-tomcat-9.0.68/webapps'
            }
        }
        stage('path'){
            steps { 
                sh './startup.sh /mnt/webserver/apache-tomcat-9.0.67/bin/'
            }
        }
        
    }
}
