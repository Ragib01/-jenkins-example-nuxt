pipeline {
     agent any
     tools {
     	nodejs 'mp-16.2.0'
     }
     environment {
        DEPLOY_DIR = '/var/www/jenkins-simple-nuxt'
     }
     stages {
        stage("Build") {
            steps {
                sh "npm install"
                sh "npm run build"
            }
        }
        stage("Deploy") {
            steps {
                sh "rm -rf ${DEPLOY_DIR}/*"
                sh "cp -r ${WORKSPACE}/dist/* ${DEPLOY_DIR}/"
                sh "chown -R www-data:www-data ${DEPLOY_DIR}"
                sh "chmod -R 755 ${DEPLOY_DIR}"
            }
        }
    }
}