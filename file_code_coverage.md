mavenJob('spring3_get_stability1') 
{
  
 
         
         customWorkspace('/var/lib/jenkins/workspace/project')
  
        mavenInstallation('mvn3.5.2')
       
        rootPOM('Spring3HibernateApp/pom.xml')
        goals('install cobertura:cobertura findbugs:findbugs checkstyle:checkstyle')
}
