FROM java:openjdk-8-jre
MAINTAINER Ching Chow

ARG SELENIUM_VERSION=2.53
ARG SELENIUM_PATCH=0
ARG CHROMEDRIVER_VERSION=2.21
ARG DISPLAY=:0

ENV DISPLAY ${DISPLAY}

COPY entropy_* /usr/local/bin/
COPY selenium /opt/selenium/

RUN set -x \
        && gpg --keyserver pgp.mit.edu --recv-keys 3EE67F3D0FF405B2 \
        && gpg --export 3EE67F3D0FF405B2 | apt-key add - \
        && echo 'deb http://packages.linuxmint.com debian import' > /etc/apt/sources.list.d/mint.list \
        && rm -rf /root/.gnupg \
        \
        && wget -nv -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add - \
        && echo 'deb http://dl.google.com/linux/chrome/deb/ stable main' > /etc/apt/sources.list.d/google-chrome.list \
        \
        && apt-get -q update && apt-get -qy --no-install-recommends install \
               firefox \
               google-chrome-stable \
               haveged \
               xvfb \
        \
        && rm -rf /var/lib/apt/lists/*

RUN set -x \
        && wget -nv -O /opt/selenium/selenium-server.jar http://selenium-release.storage.googleapis.com/${SELENIUM_VERSION}/selenium-server-standalone-${SELENIUM_VERSION}.${SELENIUM_PATCH}.jar \
        && wget -nv http://chromedriver.storage.googleapis.com/${CHROMEDRIVER_VERSION}/chromedriver_linux64.zip \
        && unzip chromedriver_linux64.zip -d /opt/selenium \
        && rm chromedriver_linux64.zip \
        && ln -s /opt/selenium/chromedriver /usr/local/bin \
        && ln -s /opt/selenium/selenium /usr/local/bin

EXPOSE 4444

WORKDIR /opt/selenium/
