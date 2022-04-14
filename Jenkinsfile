@Library("shared-lib-basic") _

def method1() {
  echo 'method1 called'
}

echo 'Basic'
method1()

static Map<String, Object> secret(String secretName, String envVariable) {
  [$class     : 'AzureKeyVaultSecret',
   secretType : 'Secret',
   name       : secretName,
   envVariable: envVariable
  ]
}

def secrets = [
  's2s-env': [
    secret('microservicekey-ccd-gw', 'CCD_API_GATEWAY_S2S_SECRET'),
    secret('microservicekey-ccd-data', 'CCD_DATA_STORE_S2S_SECRET'),
    secret('microservicekey-ccd-definition', 'CCD_DEFINITION_STORE_S2S_SECRET')
  ],
  'civil-prod': [
    secret('microservicekey-civil-service', 'S2S_SECRET_PROD')
  ]
]



pipeline {
    agent any
    

      
    stages {
        stage('Hello') {
            steps {
                println "groovy print"
                echo sh(script: 'env|sort', returnStdout: true)
                welcome("steed")
            }
        }
    }
}