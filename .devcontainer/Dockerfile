FROM payara/micro

ENV ALLOW_PLANTUML_INCLUDE true

USER root
# git is needed by VS Code Server
RUN apk update && apk add --no-cache git \
    # PlantUML dependencies
    graphviz font-noto

COPY plantuml.war $DEPLOY_DIR
RUN echo "nohup java -jar /opt/payara/payara-micro.jar --deploymentDir $DEPLOY_DIR --nocluster >> payara.out 2>&1 &" > /usr/sbin/plantuml.sh
RUN chmod a+x /usr/sbin/plantuml.sh
USER payara