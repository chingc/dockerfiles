FROM ubuntu:16.04
MAINTAINER Ching Chow

ENV SELENIUM_RELEASE 2.52
ENV SELENIUM_VERSION 2.52.0
ENV SELENIUM_URL http://selenium-release.storage.googleapis.com/${SELENIUM_RELEASE}/selenium-server-standalone-${SELENIUM_VERSION}.jar

ENV CHROMEDRIVER_VERSION 2.21
ENV CHROMEDRIVER_URL http://chromedriver.storage.googleapis.com/${CHROMEDRIVER_VERSION}/chromedriver_linux64.zip

ENV DISPLAY :0
ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64/jre

# install stuff
RUN set -x \
        && apt-get -q update && apt-get -qy install \
               wget \
        \
        && wget -nv -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add - \
        && echo 'deb http://dl.google.com/linux/chrome/deb/ stable main' > /etc/apt/sources.list.d/google-chrome.list \
        \
        && apt-get -q update && apt-get -qy install \
               firefox \
               google-chrome-stable \
               openjdk-8-jre-headless \
               unzip \
               xvfb \
        \
        # see https://bugs.debian.org/775775
        # and https://github.com/docker-library/java/issues/19#issuecomment-70546872
        && /var/lib/dpkg/info/ca-certificates-java.postinst configure \
        \
        && wget -nv -O /usr/local/bin/selenium-server.jar ${SELENIUM_URL} \
        && wget -nv -O /usr/local/bin/chromedriver.zip ${CHROMEDRIVER_URL} \
        && unzip -d /usr/local/bin/ /usr/local/bin/chromedriver.zip \
        && rm /usr/local/bin/chromedriver.zip \
        \
        && apt-get -qy --purge remove unzip \
        && apt-get -qy --purge autoremove \
        && apt-get -qy clean \
        && rm -rf /var/lib/apt/lists/*

COPY ["java_home", "selenium", "/usr/local/bin/"]

EXPOSE 4444

ENTRYPOINT ["/usr/local/bin/selenium"]
CMD [""]
