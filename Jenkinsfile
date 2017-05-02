#!groovy
node {
   stage ('Build') {
 
    git url: 'https://github.com/yogeshkumararora/experiments.git'
 
    withMaven(
       jdk: 'Java8',
        // Maven installation declared in the Jenkins "Global Tool Configuration"
        maven: 'M3',
        // Maven settings.xml file defined with the Jenkins Config File Provider Plugin
        // Maven settings and global settings can also be defined in Jenkins Global Tools Configuration
        mavenSettingsConfig: 'my-maven-settings',
        mavenLocalRepo: '.repository') {
 
      // Run the maven build
      sh "mvn clean install"
 
    } // withMaven will discover the generated Maven artifacts, JUnit reports and FindBugs reports
  }
   
   stage ('SonarQube - Code Quality and Unit Tests') {
   }
   
   stage ('AppScan - App Security Checks') {
   }
   
   stage ('Deploy to Dev Env') {
   }
   
   stage ('Integration Testing on Dev Env using Selenium/Tosca/LISA') {
   }
   
   stage ('Deployed to SIT Env') {
   }
   
   stage ('Functional Testing on SIT Env using Selenium/Tosca/LISA') {
   }
   
   stage ('Deployed to DPE Env') {
   }
   
   stage ('JMeter - Performance Testing on DPE Env') {
   }
   
   stage ('Release to PROD') {
   }
   
}
