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
                    sh 'mvn install'
                }
            }
        }
        stage('deploy to tomcat dev1')    //5 min
   {steps { sshagent (credentials: ['test']) 
     {
      sh 'scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/test3/target/jenkins-example-1.0-SNAPSHOT.jar
[INFO]  ec2-user@172.31.18.254:/usr/share/tomcat/webapps'
    } }}

    }
}