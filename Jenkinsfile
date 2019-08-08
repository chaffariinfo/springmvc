pipeline {
agent any
stages{
  stage('Build'){
    steps{
    bat 'mvn compile'
    }
  }
  stage('Reporting'){
    steps{
    cucumber failedFeaturesNumber: -1, failedScenariosNumber: -1, failedStepsNumber: -1, fileIncludePattern: '**/*.json', pendingStepsNumber: -1, skippedStepsNumber: -1, sortingMethod: 'ALPHABETICAL', undefinedStepsNumber: -1
    }
  }
}
}
