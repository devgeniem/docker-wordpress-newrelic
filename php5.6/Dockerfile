FROM devgeniem/wordpress-server:php5.6

ENV PHP_AGENT_PACKAGE="newrelic-php5-6.8.0.177-linux-musl" \
    NR_INSTALL_SILENT=1

RUN curl -L "https://download.newrelic.com/php_agent/release/$PHP_AGENT_PACKAGE.tar.gz" | \
    tar -xvzC /tmp/ && \
    mv /tmp/$PHP_AGENT_PACKAGE /var/lib/newrelic && \
    /var/lib/newrelic/newrelic-install install

COPY system-root/ /
