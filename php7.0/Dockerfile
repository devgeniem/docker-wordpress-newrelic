FROM devgeniem/wordpress-server:php7.0

# even php7.0 Uses php5.6 packages. Strange huh?
ARG PHP_AGENT_PACKAGE="newrelic-php5-8.1.0.209-linux-musl"
ENV NR_INSTALL_SILENT=1

RUN curl -L https://download.newrelic.com/php_agent/release/${PHP_AGENT_PACKAGE}.tar.gz | \
    tar -xvzC /tmp/ && \
    mv /tmp/${PHP_AGENT_PACKAGE} /var/lib/newrelic && \
    /var/lib/newrelic/newrelic-install install && \
    cd /var/lib/newrelic && \
    # Remove unneccesary stuff after installation
    rm -rf scripts newrelic-install daemon

COPY system-root/ /

RUN apk update 
RUN	apk add python