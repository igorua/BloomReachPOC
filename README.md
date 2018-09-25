# BloomReachPOC

Go to the project's root folder and run:
mvn clean verify
mvn -Pcargo.run

Open links
http://localhost:9080/cms
http://localhost:9080/cms/console
http://localhost:9080/essentials
http://localhost:9080/site/

If you have unexpected compilation error due to missing artifacts - delete folder ".m2" and rerun command: mvn clean verify
If your browser shows "Too many redirects" - clean up cookies and cache.

To change http and debug ports - open pom.xml in project's root folder and update section: 
   <groupId>org.codehaus.cargo</groupId>
   <artifactId>cargo-maven2-plugin</artifactId>
   <configuration>
     <configuration>
       <properties>
         <cargo.servlet.port>9080</cargo.servlet.port>
         <cargo.tomcat.ajp.port>9009</cargo.tomcat.ajp.port>
         <cargo.rmi.port>9205</cargo.rmi.port>
         <cargo.jvmargs>
           <![CDATA[-agentlib:jdwp=transport=dt_socket,address=9000,server=y,suspend=n -noverify ${javaagent}]]>
         </cargo.jvmargs>
       </properties>
	   
