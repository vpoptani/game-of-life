pipeline {
     agent any
     stages {
         stage('Checkout') {
             when {
                 branch 'master'
             }
             steps {
                 git credentialsId: 'Vishal Git Credentails', url: 'https://github.com/vpoptani/game-of-life.git'
             }
             post {
                 always {
                     jiraSendDeploymentInfo environmentId: 'dhs-stage-01', environmentName: 'Alcon Staging Environment', environmentType: 'staging', site: 'dhs-ops.atlassian.net'
                     jiraSendBuildInfo branch: 'master', site: 'dhs-ops.atlassian.net'
                 }
             }
         }
         
     }
 }
