#------------------------------------------------------------------------------------------------------
#	Defines an image 
#
#----------------------------------------------------------------------------------------------------

FROM java7

#Create the target directory
mkdir -p /opt/drill 


#Retrieve Apache Drill 
RUN curl -o apache-drill-1.4.0.tar.gz https://wpcp-artifactory.corp.ad.ctc/artifactory/generic-test-local/analytics/apache-drill-1.4.0.tar.gz && \
	tar zxpf apache-drill-1.4.0.tar.gz -C /opt/drill 

#Expose Web Console and ODBC/JDBC Ports	
EXPOSE 8047, 31010

#Start Server
CMD ['/opt/drill/bin/drill-embedded']