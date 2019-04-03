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
    withCredentials([azureServicePrincipal('8a589de9-4f46-451a-a6b5-bc05ba8f6f54')]) {
      sh '''
        az login --service-principal -u $AZURE_CLIENT_ID -p $AZURE_CLIENT_SECRET -t $AZURE_TENANT_ID
        az account set -s $AZURE_SUBSCRIPTION_ID
	az resource list
      '''
    }
   
    sh 'az logout'
  }
}
