# selenium-server

Selenium automates browsers.


## Description

This `Dockerfile` will build an image that contains Google Chrome, Mozilla Firefox, and the Selenium Standalone Server.  It also installs Xvfb to allow browsers to run headlessly within the container and tests to take screenshots.


## Build

`$ docker build -t selenium-server .`


## Run

`$ docker run --rm -it -p 4444:4444 selenium-server`


## Help

`$ docker run --rm selenium-server -help`

Website: http://www.seleniumhq.org/
