pipeline{
 tools{
        jdk 'JAVA_HOME'
        maven 'M2_HOME'
    }
     agent any	  
stages{	  
	  stage("checkout"){
	   steps{
	   git 'https://github.com/GitLipun/MavenTest1.git'
	   }	 
        }	
	   stage("compile"){
	    steps{
		 sh 'mvn compile'
		}
		}
       stage("test"){
	    steps{
		 sh 'mvn test'
		}
		}
       stage("package"){
	    steps{
		 sh 'mvn clean package'
                 sh "mv target/*.jar target/myapp.war"
		}
		}
	stage("deploy"){
     steps{
   
        sshagent(['c409502f-7a66-41e0-9b02-dcf466ef9e76'])
     {
    

    
   
        sh """
                 
            scp -o StrictHostKeyChecking=no target/myweb.war ec2-user@65.0.176.201:/home/ec2-user/tomcat10/webapps/

              ssh ec2-user@65.0.176.201 /home/ec2-user/tomcat10/bin/shutdown.sh
              ssh ec2-user@65.0.176.201 /home/ec2-user/tomcat10/bin/startup.sh
            
          
          """



    // some block
}
  }
  }
   }
 }
    
