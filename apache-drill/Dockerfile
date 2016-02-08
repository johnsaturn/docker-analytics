#------------------------------------------------------------------------------------------------------
#	Defines an image 
#
#----------------------------------------------------------------------------------------------------

FROM java

#Create the target directory
RUN mkdir -p /opt/drill 


#Retrieve Apache Drill 
RUN curl --insecure -o apache-drill-1.4.0.tar.gz https://wpcp-artifactory.corp.ad.ctc/artifactory/generic-test-local/analytics/apache-drill-1.4.0.tar.gz && \
	tar zxpf apache-drill-1.4.0.tar.gz -C /opt/drill 

#Expose Web Console and ODBC/JDBC Ports	
EXPOSE 8047 31010

ENV DRILL_MAX_DIRECT_MEMORY 1GB
ENV DRILL_HEAP 256B
ENV DRILL_MAX_HEAP 512MB

#Start Server
CMD ['/opt/drill/bin/drill-embedded']