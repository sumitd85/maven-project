pipeline

{
agent any
stages 
{ 
stage ('scm checkout')
{
steps { git branch: 'master', url: 'https://github.com/sumitd85/maven-project'
}}

stage ('build maven project & execute sonar')

{
 steps 
 { 
   withSonarQubeEnv('sonarqube') {
     withMaven(jdk: 'JAVA_HOME', maven: 'M2_HOME') {
                   sh 'mvn clean sonar:sonar package'
}
 }
 }}
}
}
