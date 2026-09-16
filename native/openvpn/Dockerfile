FROM alpine:3.22
RUN apk add --no-cache openvpn easy-rsa iptables openssl iproute2
COPY entrypoint.sh /usr/local/bin/nini-openvpn
RUN chmod 755 /usr/local/bin/nini-openvpn
EXPOSE 1194/udp
ENTRYPOINT ["/usr/local/bin/nini-openvpn"]
