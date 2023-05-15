pipeline {
     agent any
     stages {
        stage("Build") {
            steps {
                sh "npm install"
                sh "npm run build"
            }
        }
        stage("Deploy") {
            steps {
                shsteps {
                sh "sudo rm -rf /var/www/jenkins-simple-nuxt"
                sh "sudo mkdir -p /var/www/jenkins-simple-nuxt"
                sh "sudo cp -r ${WORKSPACE}/dist /var/www/jenkins-simple-nuxt/"
                sh "sudo chown -R www-data:www-data /var/www/jenkins-simple-nuxt"
                sh "sudo chmod -R 755 /var/www/jenkins-simple-nuxt"
            }
        }
    }
}