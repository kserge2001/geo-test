pipeline{
    agent any 
    stages{
    stage('maven clean'){
        steps{
           sh '/opt/maven/bin/mvn clean' 
        }
    }
    stage('maven install'){
        steps{
            sh 'mvn install'
            
        }
    }
    stage('maven package'){
        steps{
            sh 'mvn package'
        }
    }


    }

}