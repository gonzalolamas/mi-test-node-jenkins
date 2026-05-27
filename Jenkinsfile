pipeline {
    agent any

    stages {
        stage('Instalar Dependencias') {
            steps {
                echo 'Buscando actualizaciones...'
                // Aquí podrías poner "bat 'npm install'" si tuvieras un package.json
            }
        }
        stage('Ejecutar Test') {
            steps {
                echo 'Arrancando el Hola Mundo de Node...'
                bat 'node app.js'
            }
        }
    }
}
