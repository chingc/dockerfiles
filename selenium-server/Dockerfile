FROM java:openjdk-8-jre
MAINTAINER Ching Chow <https://github.com/chingc>

ARG SELENIUM_URL=http://selenium-release.storage.googleapis.com/2.53/selenium-server-standalone-2.53.0.jar
ARG CHROMEDRIVER_URL=http://chromedriver.storage.googleapis.com/2.21/chromedriver_linux64.zip
ARG DISPLAY=:0

ENV DISPLAY ${DISPLAY}

RUN set -x \
        && gpg --keyserver pgp.mit.edu --recv-keys 3EE67F3D0FF405B2 \
        && gpg --export 3EE67F3D0FF405B2 | apt-key add - \
        && echo 'deb http://packages.linuxmint.com debian import' > /etc/apt/sources.list.d/mint.list \
        && rm -rf /root/.gnupg

RUN set -x \
        && wget -nv -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add - \
        && echo 'deb http://dl.google.com/linux/chrome/deb/ stable main' > /etc/apt/sources.list.d/google-chrome.list

RUN set -x \
        && apt-get -q update && apt-get -qy --no-install-recommends install \
               firefox \
               google-chrome-stable \
               xvfb \
        && rm -rf /var/lib/apt/lists/*

RUN set -x \
        && wget -nv --show-progress --progress=dot:mega -P /opt/selenium ${SELENIUM_URL}

RUN set -x \
        && wget -nv --show-progress --progress=dot:mega ${CHROMEDRIVER_URL} \
        && unzip chromedriver_linux64.zip -d /opt/selenium \
        && rm chromedriver_linux64.zip

RUN set -x \
        && ln -s /opt/selenium/selenium-* /opt/selenium/selenium-server.jar \
        && ln -s /opt/selenium/chromedriver /usr/local/bin \
        && ln -s /opt/selenium/selenium /usr/local/bin

COPY selenium /opt/selenium/

EXPOSE 4444

WORKDIR /opt/selenium/

ENTRYPOINT ["selenium"]
CMD [""]
