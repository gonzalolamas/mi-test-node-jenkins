pipeline {
    agent any
    stages {
        stage('Build & Run') {
            steps {
                // Ejecuta la aplicación Node.js
                bat 'node app.js'

                // CREA LA CARPETA Y EL ARCHIVO HTML MANUALMENTE
                // Esto crea una carpeta llamada 'reportes' y un archivo 'index.html' dentro
                bat 'mkdir reportes'
                bat 'echo ^<html^>^<body^>^<h1^>Reporte de Ejecucion^</h1^>^<p^>La aplicacion app.js se ejecuto correctamente.^</p^>^</body^>^</html^> > reportes\\index.html'
            }
        }
    }
    post {
        always {
            // CONFIGURACIÓN CORRECTA DE HTML PUBLISHER
            publishHTML([
                allowMissing: false,
                alwaysLinkToLastBuild: true,
                keepAll: true,
                reportDir: 'reportes',          // Nombre de la carpeta que creamos arriba
                reportFiles: 'index.html',     // Nombre del archivo dentro de esa carpeta
                reportName: 'Reporte HTML',    // Título que veo en Jenkins
                reportTitles: ''
            ])
        }
    }
}
