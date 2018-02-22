pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                sh ' echo "Fase de test completa."'
            }
        }
    }
    environment {
        DESTINATION_SERVER = 'www-data@130.211.66.72'
        DESTINATION_PATH = '/var/www/develop/web/tienda-online/'
        DESTINATION_CONFIGRB = './skin/frontend/pesc/default'
        RSYNC_PARAMS = '-rlvv --del --exclude=.git --exclude=.gitignore  --exclude=rsync.log -exclude-from='.gitignore' --log-file=rsync.log  
    }
}
