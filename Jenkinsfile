node { 
    stage('Clone repository') { 
        git credentialsId: 'github-access', url: 'https://github.com/kmyourim/rolling-paper-fr.git' 
    } 
 
    stage('Build image') { 
       dockerImage = docker.build("imyourkm/node-front:1.0") 
    } 
 
 stage('Push image') { 
        withDockerRegistry([ credentialsId: "docker-access", url: "" ]) { 
        dockerImage.push() 
        } 
    } 
}
