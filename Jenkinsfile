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
   
   stage ('Code Quality (SonarQube)') {
      // requires SonarQube Scanner 2.8+
       def scannerHome = tool 'SonarQubeScanner';
       withSonarQubeEnv('SonarQube-5.6.6') {
         sh 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.2:sonar'
       }
   }
   
   stage ('Security Testing (AppScan)') {
   }
   
   stage ('Deploy to Dev Env') {
   }
   
   stage ('Integration Testing (Tosca/LISA)') {
   }
   
   stage ('Deployed to SIT Env') {
   }
   
   stage ('Functional Testing (Selenium/Tosca/LISA)') {
   }
   
   stage ('Deployed to DPE Env') {
   }
   
   stage ('Performance Testing (JMeter)') {
   }
   
   stage ('Release to PROD') {
   }
   
}
