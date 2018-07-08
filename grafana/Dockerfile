FROM grafana/grafana:latest
ARG GF_INSTALL_PLUGINS="grafana-clock-panel,grafana-simple-json-datasource"

MAINTAINER deshike22@gmail.com

USER grafana

RUN if [ ! -z "${GF_INSTALL_PLUGINS}" ]; then \
    OLDIFS=$IFS; \
        IFS=','; \
    for plugin in ${GF_INSTALL_PLUGINS}; do \
        IFS=$OLDIFS; \
        grafana-cli --pluginsDir "$GF_PATHS_PLUGINS" plugins install ${plugin}; \
    done; \
fi
