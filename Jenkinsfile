pipeline {
     agent any
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
                sh "sudo rm -rf ${DEPLOY_DIR}/*"
                sh "sudo cp -r ${WORKSPACE}/dist/* ${DEPLOY_DIR}/"
                sh "sudo chown -R www-data:www-data ${DEPLOY_DIR}"
                sh "sudo chmod -R 755 ${DEPLOY_DIR}"
            }
        }
    }
}