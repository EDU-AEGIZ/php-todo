pipeline {
    agent any

  stages {

     stage("Initial cleanup") {
          steps {
            dir("${WORKSPACE}") {
              deleteDir()
            }
          }
        }

    stage('Checkout SCM') {
      steps {
            git branch: 'main', url: 'https://github.com/EDU-AEGIZ/php-todo.git'
      }
    }

    stage('Execute Unit Tests') {
      steps {
             sh './vendor/bin/phpunit'
            //  sh 'composer install'
            //  sh 'php artisan migrate'
            //  sh 'php artisan db:seed'
            //  sh 'php artisan key:generate'
      }
    }
  }
 }