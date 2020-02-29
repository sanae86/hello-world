node {
  stage('SCM Checkout'){
    git credentialsId: 'git-cred', url: 'https://github.com/sanae86/hello-world.git'
  }
  stage('Mvn clean Package'){
	   // Build using maven
	  sh 'mvn clean package'
  }
}
