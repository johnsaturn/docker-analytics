#------------------------------------------------------------------------------------------------------
#	Defines an image for Pentaho Data Integrator
#
#----------------------------------------------------------------------------------------------------

FROM java

# Init ENV
ENV PENTAHO_VERSION 6.0
ENV PENTAHO_TAG 6.0.1.0-386

ENV PENTAHO_HOME /opt/pentaho

# Apply JAVA_HOME
RUN . /etc/environment
# ENV PENTAHO_JAVA_HOME /usr/lib/jvm/java-1.7.0-openjdk-amd64

# Create Pentaho Home
RUN mkdir ${PENTAHO_HOME}; useradd -s /bin/bash -d ${PENTAHO_HOME} pentaho; chown pentaho:pentaho ${PENTAHO_HOME}

USER pentaho

# Download Pentaho BI Server
RUN /usr/bin/wget --progress=dot:giga http://downloads.sourceforge.net/project/pentaho/Data%20Integration/${PENTAHO_VERSION}/pdi-ce-${PENTAHO_TAG}.zip -O /tmp/pdi-ce-${PENTAHO_TAG}.zip; \
    /usr/bin/unzip -q /tmp/pdi-ce-${PENTAHO_TAG}.zip -d  $PENTAHO_HOME; \
     rm /tmp/pdi-ce-${PENTAHO_TAG}.zip

COPY scripts/ /opt/pentaho/data-integration/
COPY slave_dyn.xml /opt/pentaho/data-integration/

WORKDIR /opt/pentaho/data-integration

EXPOSE 8181

CMD ["./carte.sh", "0.0.0.0", "8181"]
