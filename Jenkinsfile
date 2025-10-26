pipeline {
    agent any

    stages {
        stage('Preparar entorno') {
            steps {
                echo "Creando entorno virtual..."
                bat '"C:\\Users\\Angela\\AppData\\Local\\Programs\\Python\\Python313\\python.exe" -m venv venv'
                bat 'venv\\Scripts\\activate && pip install -r requirements.txt'
            }
        }
        stage('Ejecutar script1') {
            steps {
                echo "Ejecutando script 1..."
                bat 'venv\\Scripts\\activate && python numpy.py'
            }
        }
        
        stage('Ejecutar script2') {
            steps {
                echo "Ejecutando script 2..."
                bat 'venv\\Scripts\\activate && python proyecto.py'
            }
        }
  }

  post {
      success { 
          echo "✅ Pipeline completado con éxito" 
      }
      failure { 
          echo "❌ Error en alguna etapa del pipeline" 
      }
  }
}
