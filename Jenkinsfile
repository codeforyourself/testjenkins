import groovy.json.JsonSlurper


node {
  stage('init') {
    checkout scm
  }
  
  stage('build') {
   
  }
  
  stage('deploy') {
    def resourceGroup = 'test1jenkins' 
  
    // login Azure
    withCredentials([azureServicePrincipal('<mySrvPrincipal>')]) {
      sh '''
        az login --service-principal -u $AZURE_CLIENT_ID -p $AZURE_CLIENT_SECRET -t $AZURE_TENANT_ID
        az account set -s $AZURE_SUBSCRIPTION_ID
	az resource list
      '''
    }
   
    sh 'az logout'
  }
}
