node {
  stage('SCM Checkout'){
     git credentialsId: 'git-cred', url: 'https://github.com/sanae86/hello-world.git'
  }
  stage('Mvn clean Package'){
	   // Build using maven
     def mvn = tool (name: 'maven3', type: 'maven') + '/bin/mvn'
     sh "${mvn} clean package"
  }
  stage('SonarQube Analysis') {
      def mvnHome =  tool name: 'maven3', type: 'maven'
      withSonarQubeEnv('sonar-6') { 
       sh "${mvn}/bin/mvn sonar:sonar"
        }
    }
  stage('slack notification'){
     slackSend baseUrl: 'https://hooks.slack.com/services/', 
	channel: '#demo_jenkins-slack', color: 'good', message: 'welcome to jenkins', 
	tokenCredentialId: 'slack-demo'
  }
}
