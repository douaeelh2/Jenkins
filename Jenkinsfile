pipeline {
    agent any  // Utilise n'importe quel agent pour exécuter la pipeline

    stages {
        stage('Checkout') {
            steps {
                // Récupérer le code à partir de Git
                git 'https://github.com/douaeelh2/Jenkins'
            }
        }

        stage('Compile') {
            steps {
                // Compiler les fichiers Java avec javac
                script {
                    sh 'javac HelloWorld.java Merci.java DeRien.java'
                }
            }
        }

        stage('Run') {
            steps {
                // Exécuter les fichiers Java compilés
                script {
                    sh 'java HelloWorld'   // Exécuter HelloWorld
                    sh 'java Merci'        // Exécuter Merci
                    sh 'java DeRien'       // Exécuter DeRien
                }
            }
        }
    }

    post {
        success {
            echo 'La pipeline s\'est exécutée avec succès !'
        }
        failure {
            echo 'La pipeline a échoué.'
        }
    }
}
