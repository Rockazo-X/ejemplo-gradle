pipeline {
    agent any
    stages {
        stage("Pipeline"){
            steps {
                script{
                    stage("Paso 0: Download Code and checkout"){
                        // code
                    }
                    stage("Paso 1: Build && Test"){
                        // code
                    }
                    stage("Paso 2: Sonar - Análisis Estático"){
                        sh "echo 'Análisis Estático!'"
                        // code
                    }
                    stage("Paso 3: Curl Springboot Gradle sleep 20"){
                        // code
                    }
                    stage("Paso 4: Subir Nexus"){
                        // code
                    }
                    stage("Paso 5: Descargar Nexus"){
                        // code
                    }
                    stage("Paso 6: Levantar Artefacto Jar"){
                        // code
                    }
                    stage("Paso 7: Testear Artefacto - Dormir(Esperar 20sg) "){
                        // code
                    }
                }
            }
            post {
                always {
                    sh "echo 'fase always executed post'"
                }
                success {
                    sh "echo 'fase success'"
                }
                failure {
                    sh "echo 'fase failure'"
                }
            }
        }
    }
}