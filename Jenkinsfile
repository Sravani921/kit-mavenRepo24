pipeline {
    agent any
   tools {
             maven "test-maven"
   }
  stages{
         stage('checkout ') {
           
            steps {
              echo 'cloning..'
            git 'https://github.com/Sravani921/kit-mavenRepo24.git'
            }
        }
        stage("code compile"){
          
            steps{
              echo'compiling'
                sh "mvn compile"
            }
        }
        stage("codeReview"){
          
            steps{
              
              echo'codeReview'
                sh "mvn pmd:pmd"
            }
        }
        stage("UnitTest"){
          
            steps{
              
                sh "mvn test"
            }
            post{
            success{
              junit "target/surefire-reports/".xml'
            }
            }
        }
    
        stage("package"){
          
            steps{
              
                sh "mvn package"
            }
        }

    
    }
}
       
