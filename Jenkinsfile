

String registry = "dogandemir51"
String repository="parametrik deger"

pipeline {
    agent any
    tools{
    maven 'Maven3'
    }
     stages {

         stage("with mvn build project") {

           // git 'https://github.com/denizturkmen/SpringBootMysqlCrud.git'
                          echo "Java VERSION"
                          sh 'java -version'
                          echo "Maven VERSION"
                          sh 'mvn -version'
                          echo 'building project...'
                         // sh "mvn compile"
                         // sh "mvn package"
                          //sh "mvn test"
                          sh "mvn clean install"
         }
         stage("docker build image"){
         sh  ' docker build -f Dockerfile -t javadevops:v2 . '
         }
         stage("Docker Push Image"){
          //sh 'docker push $registry/$repository:${version.replaceFirst(/^.*\//, '')}-${createDate}'
         }
         stage("docker delete local images"){
          sh 'docker rmi -f javadevops:v2'

         }

     }
}