pipeline {
    agent any
    stages{
        stage('build project'){
            steps{
                git url:'https://github.com/Akansha-310/star-agile-health-care.git', branch: "master"
                sh 'mvn clean package'
              
            }
        }
        stage('Build docker image'){
            steps{
                script{
                    sh 'docker build -t akanshaaws/star-agile-health-care:latest .'
                    sh 'docker images'
                }
            }
        }
         
        
     stage('Deploy') {
            steps {
                sh 'sudo docker run -itd --name star-agile-health-care -p 8083:8080 akanshaaws/star-agile-health-care:latest'
                  
                }
            }
        
    }
}
