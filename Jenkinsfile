pipeline {
    agent any
        stages {
        stage('git repo & clean') {
            steps {
                
                git credentialsId: 'Harshagitcre', url: 'https://github.com/Harsha21397/spring-boot-hello-world.git'
            }
        }
		}
        stage('mvn install') {
            steps {
			
                sh "mvn install clean install"
            }
        }
        
        stage('mvn install') {
            steps {
                sh "mvn clean install"
                //sh 'cp -f sgpf-itembank/ib/Dockerfile /home/ec2-user/.jenkins/workspace/ib-dev-docker-build-3/'
              //  sh 'cp -f sgpf-itembank/ib/target/ib-0.0.1-SNAPSHOT.jar /home/ec2-user/.jenkins/workspace/ib-dev-docker-build-3/'
                
            }
        }
 
            // Building Docker images
    stage('Building image') {
      steps{
        script {
           sh 'docker build -t helloworld'
        }
      }
    } 
    // Uploading Docker images
    stage('Pushing to docker') {
     steps{
         script {
                 This step should not normally be used in your script. Consult the inline help for details.
                 withDockerRegistry(credentialsId: 'e051c2f9-f61a-409b-a73e-2031c8d2c586', url: 'https://hub.docker.com/repository/docker/harsha2018/simplepush') {
    some block
             } 
           }
        }
      }

    }
