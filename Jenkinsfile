pipeline {
    agent any
    stages{
        stage(clone){
            steps{
                 git "https://github.com/ramyaramana/java-maven-app.git"
                 
                 echo "i am in here clone"
                
            }
        }
        stage(build){
            steps{
                 sh "mvn clean install -DskipTests"
                 
                 echo "i am in here build"
                
            }
        }
        stage(test){
            steps{
                 sh "mvn test"
                 
                 echo "i am in here"
                
            }
            post {
                always {
                    junit "target/surefire-reports/*.xml"
                    archiveArtifacts "target/*.jar"
                }
            }
        }
         stage(run){
            steps{
                sh "./scripts/deliver.sh"
                  
                 echo "i am in here"
                
            }
         }
         stage(utest){
            steps{
                
                  
                 echo "i am in here utest"
                
            }
        }
    }
    
}
