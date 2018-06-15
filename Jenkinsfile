#!/usr/bin/env groovy

node {
    stage 'Checkout'
        checkout scm

    stage 'Clean'
        bat 'gradlew clean'

    stage 'Test'
        bat 'gradlew test'

    stage('Publish')
    {
        junit 'build/test-results/**/*.xml'
        publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'build/reports/tests/test', reportFiles: 'index.html', reportName: 'HTML Report', reportTitles: ''])
    }
}