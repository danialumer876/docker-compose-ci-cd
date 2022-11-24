node 
{
    def app

    stage('Clone repository') {

        checkout scm
    }

    stage('Build image') {


        app = docker.build("docker-compose-ci-cd")
    }
    
    stage('Run Docker Compose') {
  
        sh '''( docker-compose down && docker-compose up -d ) || (docker-compose up -d )
'''
        
//         def containerExists = sh(returnStdout: true, script: 'docker ps -a -f name=html_docker_jenkins_ci_cd' ) 

//         if(containerExists){
//             sh 'docker stop html_docker_jenkins_ci_cd'
//             sh 'docker rm html_docker_jenkins_ci_cd'
//             sh 'docker run --name html_docker_jenkins_ci_cd -p 8008:80 -d html-docker-jenkins-ci-cd'

//         } else {
//             sh 'docker run --name html_docker_jenkins_ci_cd -p 8008:80 -d html-docker-jenkins-ci-cd'
//         }   
    }
  
}
    
