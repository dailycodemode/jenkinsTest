
@Library("shared-lib-basic") _

// def method1() {
//   echo 'method1 called'
// }
// echo 'Basic'
// method1()


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

def type = "nodejs"
def product = "civil"
def component = "citizen-ui"

println "START"
println("env.BRANCH_NAME:" + env.BRANCH_NAME)
println(env.BRANCH_NAME)
println(BRANCH_NAME)
println("branch Name")

withPipeline(type, product, component) {
    println("withPipeline closure")
}


// pipeline {
//     agent any
    

      
//     stages {
//         stage('Hello') {
//             steps {
//                 println "groovy print"
//                 println env.BRANCH_NAME
//                 echo sh(script: 'env|sort', returnStdout: true)
//                 welcome("steed")
//             }
//         }
//     }
// }
println "END"