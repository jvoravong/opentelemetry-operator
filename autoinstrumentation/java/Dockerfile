# To build one auto-instrumentation image for Java, please:
#  - Download your customized `javaagent.jar` to `/javaagent.jar`. This is required as when instrumenting the pod,
#    one init container will be created to copy the jar to your app's container.
#  - Grant the necessary access to the jar. `chmod -R go+r /javaagent.jar`
FROM busybox

ARG version
# Update the image to a splunk distibution  https://github.com/signalfx/splunk-otel-java/releases/download/v1.20.0/splunk-otel-javaagent-all.jar
ADD https://github.com/signalfx/splunk-otel-java/releases/download/v1.20.0/splunk-otel-javaagent-all.jar /javaagent.jar
# run  docker build .
# push the docker image to a public repo
# docker tag sha_value {repo/imagename}
#
# docker tag 391089d621df jvsplk/splunk-otel-java
# docker push jvsplk/splunk-otel-java
#
# Result:
# https://hub.docker.com/repository/docker/jvsplk/splunk-otel-java/general
# jvsplk/splunk-otel-java:latest

RUN chmod -R go+r /javaagent.jar
