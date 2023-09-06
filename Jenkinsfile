pipeline{
    agent any 
    tools{
         maven 'M2_HOME'
    }
    stages{
    stage('maven clean'){
        steps{
        sh  'mvn clean'
        }
    }
    stage('maven install'){
        steps{
          sh  'mvn install'
            
        }
    }
    stage('maven package'){
        steps{
         sh   'mvn package'
        }
    }
    stage('upload artifact'){
        steps{
            sh 'curl --upload-file target/bioMedical-0.0.2-SNAPSHOT.jar -u admin:devops -v http://198.58.119.40:8081/repository/prof-repo/'
        }
    }

    }

}