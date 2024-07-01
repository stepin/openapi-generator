FROM eclipse-temurin:17.0.9_9-jre-focal

RUN curl -sSLO https://github.com/pinterest/ktlint/releases/download/1.3.0/ktlint && \
    chmod a+x ktlint && \
    sudo mv ktlint /usr/local/bin/
ENV KOTLIN_POST_PROCESS_FILE "/usr/local/bin/ktlint -F"

ADD target/openapi-generator-cli.jar /opt/openapi-generator/modules/openapi-generator-cli/target/openapi-generator-cli.jar

COPY docker-entrypoint.sh /usr/local/bin/

ENTRYPOINT ["docker-entrypoint.sh"]

CMD ["help"]
