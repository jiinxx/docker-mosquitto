FROM alpine:3.6

EXPOSE 1883 9001

VOLUME ["/mosquitto/config", "/mosquitto/data", "/mosquitto/log"]

RUN apk --no-cache add mosquitto=1.4.12-r0 && \
    mkdir -p /mosquitto/config /mosquitto/data /mosquitto/log

COPY  include/ /

RUN chown -R mosquitto:mosquitto /mosquitto

ENTRYPOINT ["/docker-entrypoint.sh"]

CMD ["/usr/sbin/mosquitto", "-c", "/mosquitto/config/mosquitto.conf"]
