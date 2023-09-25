properties([parameters([choice(choices: ['testjenkins', 'cicdfew',], name: 'template')])])


pipeline {
  agent any
  stages {
    stage('101') {
      steps {
        echo "Few"
        echo "$template"
      }
    }
    stage('awx') {
      ansibleTower(
            towerServer: 'AWX',  // set server on AWX tower
            towerCredentialsId: 'AWX',     // User and password
            templateType: 'job',        // template type
            jobTemplate: "$template",
            towerLogLevel: 'full',
            verbose: true,
//             extraVars: '''---
// my_var:  "Jenkins Test"''',
        )
    }
  }
} 
