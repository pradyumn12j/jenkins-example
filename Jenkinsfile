pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {withMaven(globalMavenSettingsConfig: '', jdk: 'JAVA_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '', traceability: true) 
{
                    sh 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {withMaven(globalMavenSettingsConfig: '', jdk: 'JAVA_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '', traceability: true) 
{
                    sh 'mvn test'
                }
            }
        }


        stage ('Deployment Stage') {
            steps {withMaven(globalMavenSettingsConfig: '', jdk: 'JAVA_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '', traceability: true) 
{
                    sh 'mvn package'
                }
            }
        }
    }
}