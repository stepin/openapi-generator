FROM eclipse-temurin:17.0.9_9-jre-focal

RUN curl -sSLO https://github.com/pinterest/ktlint/releases/download/1.3.0/ktlint && \
    chmod a+x ktlint && \
    mv ktlint /usr/local/bin/ && \
    echo "root = true\n\n[*.{kt,kts}]\nktlint_standard_no-wildcard-imports = disabled" > /opt/ktlint-editor-config
ENV KOTLIN_POST_PROCESS_FILE "/usr/local/bin/ktlint --editorconfig=/opt/ktlint-editor-config --format"

ADD target/openapi-generator-cli.jar /opt/openapi-generator/modules/openapi-generator-cli/target/openapi-generator-cli.jar

COPY docker-entrypoint.sh /usr/local/bin/

ENTRYPOINT ["docker-entrypoint.sh"]

CMD ["help"]
