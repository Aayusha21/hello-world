pipeline {
    agent any
  tools {
      maven 'MAVEN'
  }
  stages{
    stage('build'){
      steps{
          sh script: 'mvn clean install package'
      }
    }
    stage('upload'){
      steps{
            nexusArtifactUploader artifacts: [
                [
                    artifactId: 'maven-project', 
                    classifier: '', 
                    file: 'webapp/target/webapp.war', 
                    type: 'war'
                ]
            ], 
            credentialsId: 'b55f7da2-e39e-4f4c-b8cd-2e6e94565adb', 
            groupId: 'com.example.maven-project', 
            nexusUrl: '54.90.46.123:8081', 
            nexusVersion: 'nexus3', 
            protocol: 'http', 
            repository: 'maven-snapshots', 
            version: '1.0.0-SNAPSHOT'
      }
    }
  }

}
