FROM openjdk:8-jre 
#ENV http_proxy http://192.168.10.4:3128
ADD https://s3.amazonaws.com/publicsctdownload/Ubuntu/aws-schema-conversion-tool-1.0.latest.zip .
ADD *.deb . 
RUN unzip aws-schema-conversion-tool-1.0.latest.zip
RUN apt-get update && apt-get install -y libswt-gtk-3-jni libswt-gtk-3-java  openjfx libgl1-mesa-dri
ADD xdg-desktop-menu /usr/bin/
RUN chmod +x /usr/bin/xdg-desktop-menu
RUN dpkg -i aws-schema-conversion-tool-1.0.622.deb
ADD *.jar /opt/AWSSchemaConversionTool/
RUN mkdir -p /root/AWS\ Schema\ Conversion\ Tool/
ADD ["*.xml", "/root/AWS Schema Conversion Tool/"]
CMD /opt/AWSSchemaConversionTool/AWSSchemaConversionTool