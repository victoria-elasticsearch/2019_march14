ARG ELK_VERSION


# Get apm-server images
FROM docker.elastic.co/apm/apm-server:${ELK_VERSION}
# Add your apm set up here

# Get elastic node host and port
ARG ES_HOST
ARG ES_PORT

# copy configuration file
COPY "config/apm-server.yml" "/usr/share/apm-server/apm-server.yml"

# replace host and port in config file
USER root
RUN sed -i -- "s/{{es_host}}/$ES_HOST/g" /usr/share/apm-server/apm-server.yml
RUN sed -i -- "s/{{es_port}}/$ES_PORT/g" /usr/share/apm-server/apm-server.yml