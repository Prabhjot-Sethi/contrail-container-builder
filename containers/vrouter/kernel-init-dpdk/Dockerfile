ARG CONTRAIL_REGISTRY
ARG CONTRAIL_CONTAINER_TAG
ARG CONTAINER_PREFIX
FROM ${CONTRAIL_REGISTRY}/${CONTAINER_PREFIX}-vrouter-base:${CONTRAIL_CONTAINER_TAG}
ARG VENDOR_DOMAIN

ARG CONTAINER_NAME
LABEL name=$CONTAINER_NAME \
      summary="Kernel init container for vrouter in DPDK mode" \
      description="Prepares the host operating system for the contrail vrouter dpdk interface."

RUN yum install -y contrail-vrouter-dpdk-init && \
    yum clean all -y && \
    rm -rf /var/cache/yum

COPY entrypoint.sh /

ENTRYPOINT ["/entrypoint.sh"]

LABEL $VENDOR_DOMAIN".container.name"=$CONTAINER_NAME
