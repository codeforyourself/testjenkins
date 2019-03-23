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
    withCredentials([azureServicePrincipal('18a23a03-7914-4a1a-9b67-ba14f667bdd2')]) {
      sh '''
        az login --service-principal -u $AZURE_CLIENT_ID -p $AZURE_CLIENT_SECRET -t $AZURE_TENANT_ID
        az account set -s $AZURE_SUBSCRIPTION_ID
	az resource list
      '''
    }
   
    sh 'az logout'
  }
}
