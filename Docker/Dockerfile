FROM registry.access.redhat.com/rhel7

ENV MMPP_VERSION 4.4
ENV MMPP_VERSION_MINOR .0

RUN cd /opt && \
    curl -L https://github.com/mattermost/mattermost-push-proxy/releases/download/v${MMPP_VERSION}/mattermost-push-proxy-${MMPP_VERSION}${MMPP_VERSION_MINOR}.tar.gz > mmpp.tar.gz && \
    tar xvf mmpp.tar.gz && rm mmpp.tar.gz

COPY mattermost-push-proxy.json /opt/mattermost-push-proxy/config/

RUN chmod -R 777 /opt/mattermost-push-proxy/config/
COPY docker-entrypoint.sh /

ENTRYPOINT ["/docker-entrypoint.sh"]
