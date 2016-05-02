# selenium-server

Selenium automates browsers.


## Description

This `Dockerfile` will build an image that contains Selenium Standalone Server, Mozilla Firefox, and Google Chrome.  It uses Xvfb to allow browsers to run headlessly within the container and tests to take screenshots.


## Build

`$ docker build -t selenium-server .`

#### Optional Build Arguments

- SELENIUM_VERSION
  - Version of Selenium to install.  Default: 2.53
- SELENIUM_PATCH
  - Patch version of Selenium.  The 0 in 2.53.0.  Default: 0
- CHROMEDRIVER_VERSION
  - Version of Chromedriver to install.  Default: 2.21
- DISPLAY
  - Value of the DISPLAY environmental variable.  Default: :0


## Run

`$ docker run --rm -it selenium-server`


## Help

`$ docker run --rm selenium-server -help`
