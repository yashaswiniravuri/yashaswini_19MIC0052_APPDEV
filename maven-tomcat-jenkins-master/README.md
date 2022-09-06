maven-tomcat-jenkins
====================

Its a   small  hello   world project    for  folks  starting to use  Jenkins  for   CI 


Getting Started  
====================

Prerequisite  :   Make  sure  that   you   have  java  installed  on your dev  box  .

Step  0  :
=======
Before  using   CI  it   is  always  better   to  do a   small  console check  for  your  preoject  .  Maven  provide   an  unique  functionality
called  archetypes   which can help    you  generate   some   hello   world  projects on  various   Java  based  Application
Platform .  

C:\Users\pdam>mvn  archetype::generate

[INFO] Scanning for projects...

[INFO]

[INFO] ------------------------------------------------------------------------

[INFO] Building Maven Stub Project (No POM) 1

[INFO] ------------------------------------------------------------------------

[INFO]

[INFO] >>> maven-archetype-plugin:2.2:generate (default-cli) @ standalone-pom 

[INFO] Generating project in Interactive mode

---   A long  List  of   archetypes  ---
Sample   application  to be   used 
==================================

Lets   choose  a  basic  tomcat  application  which  needs   to be  deployed  on a  tomcat instance as a    war 

Its   is   called   tomcat-maven-archetype  and  is   a   complete  webarchive  deployed to  Tomcat 6  or  7  

It  has   5  submodules  

      basic-api    Interface for   a  REST  Based  API  service  
      basic-api-impl   Implementation  of  basic-api
      basic-webapp     A  set of   HTML /JSP  Pages   where  the  service is  calle 
      basic-webapp-exec   A   binary  bundle  with   application  embeeded  as  1   war  in   tomcat 
      basc-webapp-it   Selenium   Functional  Tests    to  run   it 
      
      
Get  the  project   and   build   it   till the  test  phase  

      mvn test 
      
Step  1  
===========
    Download  jenkins   from the  site      https://wiki.jenkins-ci.org/display/JENKINS/Use+Jenkins . Its  a    war file  and  
    so   should be   abl  tto  use  it  from command  line   as  
          java  -jar  jenkins.war  
    
Step    2
==========
      Once    you have  jenkins   up and  running   ,  you  could  use   the  URL  http://localhost:8080     and   see   the  
      Jenkins  Page   .You need     to  do   some basic   configuration 
        1/   Point   jenkins    to   your  local Installtion of  java  
        2/   Point   jenkins    to   your  local Installtion of  ant 
        3/   Point   jenkins    to   your  local Installtion of  maven  
(  to  be    demonstrated  ) 

Step  3
========
       Take   note  of  your  SCM  ,  svn   in this   case   .Nore   the  project  location  and  user credentials  to be   used
       for  the  same  .   You   also  need   to  provide  a   smtp    server    details    so that  the  Test  results  can be  mailed 
       to a  target    audience 
       
       
Step   4
=========
        You   are   good  to     go  and   could  try   building  the   same  multimodule  maven project  by  specifying the  
        maven goal     "  mvn test  "
        
Step    5 
=========
       Cick    build  job   and    have  a    cup of    coffee  . The  maven artifacts   take   some time    to  download  for 
       the   first    time  .  
       
       Jenkins  has a   amazing set   of   reporting plugins and   you should  be   able    to view   all kinds   of  reports  
       Incase    you   are  wondering   maven test   will build  the  project   and  then   launch  an  embeddded   tomcat  container
       so that  your   functional  reselnium  Tests  are  also possible  to be    run   
       
       
       
        




      


