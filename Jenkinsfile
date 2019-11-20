pipeline {
agent any
stages{
  stage('Build'){
    steps{
    bat 'mvn compile'
    }
  }
  stage('Report'){
  steps{
  cucumber failedFeaturesNumber: -1, failedScenariosNumber: -1, failedStepsNumber: -1, fileIncludePattern: '**/*.json', pendingStepsNumber: -1, skippedStepsNumber: -1, sortingMethod: 'ALPHABETICAL', undefinedStepsNumber: -1
  }
  }
  stage('deploiement'){
    steps{
      nexusPublisher nexusInstanceId: 'LocalNexus', nexusRepositoryId: 'maven-releases', packages: [[$class: 'MavenPackage', mavenAssetList: [[classifier: '', extension: '', filePath: '']], mavenCoordinate: [artifactId: 'spring-mvc-form', groupId: 'com.tounga.form', packaging: 'war', version: '1.0-SNAPSHOT']]], tagName: 'spring-mvc-form'
    
    }
  }
}
}
