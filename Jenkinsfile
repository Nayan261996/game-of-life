pipeline {
    agent { label 'QA' }
    stages('deploy war'){
        stage('permission'){
            steps { 
                sh 'sudo su -'
            }
        }
        stage('copy from s3'){
            steps { 
                sh 'aws s3 cp s3://velpproj/gameoflife.war /mnt/webserver/apache-tomcat-9.0.68/webapps'
            }
        }
        stage('path'){
            steps { 
                sh 'cd /mnt/webserver/apache-tomcat-9.0.67/bin'
            }
        }
        stage('path'){
            steps { 
                sh './startup.sh'
            }
        }
    }
}
