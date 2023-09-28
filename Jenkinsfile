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
           withCredentials([[$class: 'VaultUsernamePasswordCredentialBinding', credentialsId: 'd6f5b993-23d5-4d83-a7ff-c734e8946abe', passwordVariable: 'PASSWORD', usernameVariable: 'USERNAME']]) {
                
         nexusArtifactUploader artifacts: [[artifactId: 'bioMedical',
          classifier: '', file: 'target/bioMedical-0.0.2-SNAPSHOT.jar',
           type: 'jar']], credentialsId: 'd6f5b993-23d5-4d83-a7ff-c734e8946abe', groupId: 'qa', 
           nexusUrl: '198.58.119.40:8081', 
           nexusVersion: 'nexus3', protocol: 'http',
            repository: 'prof-repo', version: '0.0.2-SNAPSHOT'  
        sh 'echo $USERNAME'
        sh  'echo $PASSWORD'
        }
    }
    }
// credentialsId: 'NexusID',
    }

}
