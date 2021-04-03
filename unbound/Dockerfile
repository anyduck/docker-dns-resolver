FROM alpine:latest

RUN apk --update --no-cache add unbound

COPY configs/unbound.conf /etc/unbound/unbound.conf

RUN /usr/bin/update-dns-root-hints

RUN mkdir -p /var/log/unbound/ && chown unbound:unbound /var/log/unbound/ && chmod 755 /var/log/unbound/

VOLUME /var/log

EXPOSE 53/tcp 53/udp

CMD ["/usr/sbin/unbound", "-d"]
