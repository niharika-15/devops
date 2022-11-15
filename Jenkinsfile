
pipeline {
    
    agent any

    

    stages {
        
       
        stage('clone scm') {
            
            steps {
                
                echo 'cloning repository'
  
                git 'https://github.com/wakaleo/game-of-life.git'         
            }
       
        }

         stage('build artifact') {
            
            steps {
                
                echo 'uildig war file'
  
                sh 'mv clean install' 
   
            }

        }

        stage('deploy to tomcat') {
            
            steps {
                
                echo 'deployig war file to tomcat'
  
                deploy adapters: [tomcat9(credentialsId: 'niharika-15', path: '', url: 'http://54.172.105.167:8080')], contextPath: 'game of life', war: '**/*.war' 
   
            }

        }

}

}
