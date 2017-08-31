FROM jenkins/jenkins:alpine

#Skip the setup wizard
ENV JAVA_OPTS="-Djenkins.install.runSetupWizard=false"

#Create username & password from environment variable JENKINS_USER_SECRET and JENKINS_PASS_SECRET
COPY security.groovy /usr/share/jenkins/ref/init.groovy.d/security.groovy

#Install the plugins required for your environment from the list provided in plugins.txt
COPY plugins.txt /usr/share/jenkins/ref/plugins.txt
RUN /usr/local/bin/install-plugins.sh < /usr/share/jenkins/ref/plugins.txt

