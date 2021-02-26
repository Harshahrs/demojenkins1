node{

   def tomcatWeb = 'C:\\Users\\Harsha\\Apache Software Foundation\\Tomcat 9.0\\webapps'
   stage('SCM Checkout'){
      git 'https://github.com/Harshahrs/demoJenkins1.git'
   }
   stage('Compile-Package-create-war-file'){
      // Get maven home path
      def mvnHome =  tool name: 'Maven 3.6.3', type: 'maven'   
      bat "${mvnHome}/bin/mvn package"
      }
/*   stage ('Stop Tomcat Server') {
               bat ''' @ECHO OFF
               wmic process list brief | find /i "tomcat" > NUL
               IF ERRORLEVEL 1 (
                    echo  Stopped
               ) ELSE (
               echo running
                  "${tomcatBin}\\shutdown.bat"
                  sleep(time:10,unit:"SECONDS") 
               )
'''
   }*/
   stage('Deploy to Tomcat'){
     bat "copy target\\demoJenkins.war \"${tomcatWeb}\\demojenkins.war\""
   }
      
}
