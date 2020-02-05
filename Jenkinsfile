pipeline {
 agents any 

  stages { 
     stage ('checkout') {
      
                steps {
                git branch: 'master', url: https://github.com/nasa7733/test01.git
                       }
             }

    stage ('set Terraform path') { 

      steps {  
           script{
             def tfHome = tool name: 'Terraform'
             env.PATH = "${tfHome}:${env.PATH}"
                  }
            sh 'terraform --version'

               }
          }

stage ('Proceed with further') {
steps {
     sh 'terraform init'
     sh 'terraform paln'
     sh 'terraform apply -auto-approve'
     }
    }
 
  }
}

