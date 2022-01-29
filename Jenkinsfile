import groovy.json.JsonSlurperClassic
def jsonParse(def json) {
    new groovy.json.JsonSlurperClassic().parseText(json)
}
pipeline {
	    agent any
	    environment {
	        NEXUS_USER         = credentials('user-admin')
	        NEXUS_PASSWORD     = credentials('user-pass')
	    }
	    parameters {
	        choice(
	            name:'compileTool',
	            choices: ['Maven', 'Gradle'],
	            description: 'Seleccione herramienta de compilacion'
	        )
	    }
	    stages {
	        stage("Pipeline"){
	            steps {
	                script{
	                  switch(params.compileTool)
	                    {
	                        case 'Maven':
	                            def ejecucion = load 'maven.groovy'
	                            ejecucion.call()
	                        break;
	                        case 'Gradle':
	                            def ejecucion = load 'gradle.groovy'
	                            ejecucion.call()
	                        break;
	                    }
	                }
	            }
	            post{
	                success{
	                    slackSend color: 'good', message: "[Diego Roco] [${JOB_NAME}] [${BUILD_TAG}] Ejecucion Exitosa", teamDomain: 'dipdevopsusac-tr94431', tokenCredentialId: 'token-slack'
	                }
	                failure{
	                    slackSend color: 'danger', message: "[Diego Roco] [${env.JOB_NAME}] [${BUILD_TAG}] Ejecucion fallida en stage [${env.TAREA}]", teamDomain: 'dipdevopsusac-tr94431', tokenCredentialId: 'token-slack'
	                }
	            }
	        }
	    }
	}

