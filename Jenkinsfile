node {
  stage('SCM Checkout'){
     git credentialsId: 'git-cred', url: 'https://github.com/sanae86/hello-world.git'
  }
  stage('Mvn clean Package'){
	   // Build using maven
     def mvn = tool (name: 'maven3', type: 'maven') + '/bin/mvn'
     sh "${mvn} clean package"
  }
}
