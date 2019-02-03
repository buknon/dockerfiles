FROM openjdk:8-jdk
# FROM openjdk:8-jdk-alpine
# FROM java:openjdk-8-jre
# ENV http_proxy http://192.168.10.4:3128
ENV VERSION 5.3.1
# ADD dbeaver-ce_5.3.1_amd64.deb . 
ADD https://github.com/dbeaver/dbeaver/releases/download/${VERSION}/dbeaver-ce_${VERSION}_amd64.deb .
RUN apt-get update && apt-get install -y libswt-gtk-3-jni libswt-gtk-3-java 
RUN dpkg -i dbeaver-ce_${VERSION}_amd64.deb

RUN echo "Starting dbeaver!!!!!" >> temp.log
CMD dbeaver & tail -f temp.log
