pipeline {
    agent any
    
    stages {
          stage('Git-Checkout') {            
              steps {
                 
                        echo "Checking out from Git repo";
                        git 'https://github.com/Celcis/jenkins-docker.git'
                               
                        }
                    }
          stage('Build') {
                steps{
                        echo  'The Project is building'
                        echo 'Builded siccessfully!'
                    }
                 }
         stage('Test') {
               steps {
                   //Crucial part the code is time out block. 
                    timeout(time: 30, unit: 'SECONDS') {
                          sh "bash ./run.sh"
                        echo 'Quality Gate passed succesfully!'
                    }
                }
            }
         stage('Deploy') {
               steps {
                        echo "Pass!"
            }
        }  
    }
}
