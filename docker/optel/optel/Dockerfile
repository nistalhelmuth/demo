ARG     TAG_VERSION
FROM    otel/opentelemetry-collector:${TAG_VERSION}
COPY    config/rewardsweb.yaml /etc/otel-agent-config.yaml
EXPOSE  13133
CMD     ["--config=/etc/otel-agent-config.yaml"]