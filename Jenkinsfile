pipeline
{
    agent any
    stages
    {
        stage('ContinuousDownload')
        {
            steps
            {
                git 'https://github.com/intelliqittrainings/maven.git'
            }
        }
        
        stage('ContinuousBuild') {
           steps {
               sh 'mvn package'
           }
      }
        stage('ContinuousDeployment')
        {
            steps
            {
               deploy adapters:[tomcat10(credentialsId:'bfb67f1d-2f4e-430c-bb8d-30584116bd00',path: '',url:'http://18.209.7.222:8080/')],contextPath:'test1',war: '**/*.war'
            }
        }
         
    }
     
    }
