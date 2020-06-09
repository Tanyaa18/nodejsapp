pipeline { 
    agent { label 'master' }
    environment{
        deployment_skipped = 'true'
    }
    tools {
        nodejs "node"
    }
    options{
        timestamps()
    }
    stages {
            //Cleaning the workspace
        stage('Clean Workspace'){
                steps {
                    deleteDir()
                }
        }   
            //Checking out Source Code
            stage('Checkout SCM'){
                steps {
                checkout([$class: 'GitSCM', branches: [[name: 'master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'Tanyaa18', url: 'https://github.com/Tanyaa18/nodejsapp.git']]])
              
                
                }    
            }    
            
    stage('Build app') {

      steps {

        bat 'npm install'

         

      }

    }  
    stage('Run the node Application') {

      steps {

        bat 'node index.js'

      }

    }
       }
  
 }    
