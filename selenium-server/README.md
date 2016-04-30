# selenium-server

Selenium automates browsers.


### Description

This `Dockerfile` will build an image that contains Selenium Standalone Server, Mozilla Firefox, and Google Chrome.  It uses Xvfb to allow browsers to run headlessly within the container and tests to take screenshots.


### Build

`$ docker build -t selenium-server .`


### Run

`$ docker run --rm -it selenium-server`


### Help

`$ docker run --rm selenium-server -help`
