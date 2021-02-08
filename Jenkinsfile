pipline {
   agent any 
     stages {
        stage("Build AApplication") {
           steps {
               sh 'mvn -f pom.xml clean package'
        }
        post {

             sucess {

               echo "Now Archiving the Artifacts...."
               archivartifacts artifacts: '***/*.war'

             }
       }
   }

   Stages ('Create Tomcat Docker Image'){
            steps {
                sh "docker build . -t tomcatsamplewebapp:${env.BUILD_ID}"
       }
  }

}


