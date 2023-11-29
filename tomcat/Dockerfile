# https://hub.docker.com/_/tomcat
FROM tomcat:9.0.83-jre21

# Add Redis session manager dependencies
COPY ./redisson-all-3.22.0.jar $CATALINA_HOME/lib/
COPY ./redisson-tomcat-9-3.22.0.jar $CATALINA_HOME/lib/

# Replace the default Tomcat context.xml with custom context.xml
COPY ./context.xml $CATALINA_HOME/conf/

# Add Redisson configuration
COPY ./redisson.yaml $CATALINA_HOME/conf/

# Expose the port Tomcat will run on
EXPOSE 8080

# Start Tomcat
CMD ["catalina.sh", "run"]