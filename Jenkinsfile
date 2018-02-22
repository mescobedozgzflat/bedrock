pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                sh ' echo "Fase de test completa."'
            }
        }
        stage('Deploy') {
            agent any
            options {
                skipDefaultCheckout()
            }
            steps {
                sh 'eval rsync $RSYNC_PARAMS ./ $DESTINATION_SERVER:$DESTINATION_PATH'
            }
        }
    }
    environment {
        DESTINATION_SERVER = 'www-data@35.227.110.165'
        DESTINATION_PATH = '/var/www/bedrock'
        DESTINATION_CONFIGRB = './skin/frontend/pesc/default'
        RSYNC_PARAMS = '-rlvv --del --exclude=.git --exclude=.gitignore  --exclude=rsync.log  --log-file=rsync.log' 
    }
}
