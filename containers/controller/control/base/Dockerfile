ARG CONTRAIL_REGISTRY
ARG CONTRAIL_CONTAINER_TAG
ARG CONTAINER_PREFIX
FROM ${CONTRAIL_REGISTRY}/${CONTAINER_PREFIX}-base:${CONTRAIL_CONTAINER_TAG}
ARG VENDOR_DOMAIN

RUN yum install -y contrail-control contrail-dns && \
    yum clean all -y && \
    rm -rf /var/cache/yum

ENV NODE_TYPE=control
LABEL $VENDOR_DOMAIN".pod"=$NODE_TYPE
CMD ["/usr/bin/tail","-f","/dev/null"]
