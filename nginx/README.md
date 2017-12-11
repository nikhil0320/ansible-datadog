This is the playbook to configure the datadog to moniter the tomcat server.
1.Run the playbook to install datadog .
2.Run the playbook to configure the tomcat.
3.Variables:
  JMX_port:It is port in which the app server sent the metrics to the particular port called jmx port

4.create a file bin/setenv.sh in the tomcat server and to enable jmxromote.port:copy the below code and execute the setenv.sh file and restart the tomcat sevrer and restart the datadog-agent

JAVA_OPTS="-Dcom.sun.management.jmxremote -Dcom.sun.management.jmxremote.port=9999 -Dcom.sun.management.jmxremote.rmi.port=9998 -Dcom.sun.management.jmxremote.ssl=false -Dcom.sun.management.jmxremote.authenticate=false "
 
  
