FROM payara/micro:5.193.1

USER root
RUN apk add --no-cache git bash libgcc libstdc++ graphviz fontconfig font-noto 

COPY plantuml.war $DEPLOY_DIR
ARG PLANTUML=/usr/sbin/plantuml.sh
RUN echo "java -jar /opt/payara/payara-micro.jar --deploydir $DEPLOY_DIR" > $PLANTUML
RUN chmod a+x $PLANTUML

USER payara