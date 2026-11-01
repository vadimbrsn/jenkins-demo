pipeline {
    agent any

    // Déclaration de variables utilisables dans tous les stages
    environment {
        APP_NAME = 'jenkins-demo'
        BUILD_ENV = 'staging'
    }

    stages {
        stage('Build') {
            steps {
                echo "Compilation de l'application ${env.APP_NAME}..."
                sh 'echo "Version de l'environnement : $BUILD_ENV"'
            }
        }
        stage('Test') {
            steps {
                echo 'Exécution des tests de recette...'
                // Simulation d'une commande système
                sh 'uptime'
            }
        }
        stage('Deploy') {
            steps {
                echo "Déploiement de ${env.APP_NAME} sur l'environnement ${env.BUILD_ENV}..."
            }
        }
    }

    // Actions exécutées à la fin du pipeline
    post {
        always {
            echo 'Nettoyage de l\'espace de travail (exécuté systématiquement).'
        }
        success {
            echo 'Le pipeline s\'est terminé avec succès !'
        }
        failure {
            echo 'Alerte : Le pipeline a échoué.'
        }
    }
}