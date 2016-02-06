#------------------------------------------------------------------------------------------------------
#	Defines an image 
#
#----------------------------------------------------------------------------------------------------

FROM java7

#Create the target directory
mkdir -p /opt/drill 

#Retrieve Apache Drill  and extract
RUN curl -o apache-drill-1.4.0.tar.gz http://apache.cs.uu.nl/drill/drill-1.4.0/apache-drill-1.4.0.tar.gz && \
	tar zxpf apache-drill-1.4.0.tar.gz -C /opt/drill 

#Expose Web Console and ODBC/JDBC Ports	
EXPOSE 8047, 31010 

#Start Server
CMD ['/opt/drill/bin/drill-embedded']