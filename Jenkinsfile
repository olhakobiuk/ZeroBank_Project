node { 
    stage('Clone code') { 
        git 'https://github.com/olhakobiuk/ZeroBank_Project.git' 
    } 
         
    stage('Run tests'){ 
        if(isUnix()){ 
            sh "mvn clean test -Dcucumber.filter.tags=\"@smoke\""
        } else { 
            bat "mvn clean test -Dcucumber.filter.tags=\"@smoke\"" 
        } 
    } 
         
    stage('Generate report'){ 
           cucumber failedFeaturesNumber: -1, failedScenariosNumber: -1, failedStepsNumber: 
-1, fileIncludePattern: '**/*.json', pendingStepsNumber: -1, skippedStepsNumber: -1, 
sortingMethod: 'ALPHABETICAL', undefinedStepsNumber: -1 
    } 
}
