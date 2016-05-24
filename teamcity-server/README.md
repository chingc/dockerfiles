# teamcity-server

Powerful continuous integration out of the box.


## Description

This `Dockerfile` will build an image that contains a TeamCity Continuous Integration Server with a Professional Server License.


## Build

`$ docker build -t teamcity-server .`


## Run

`$ docker run --rm -it -p 8111:8111 teamcity-server`

Once the container is running, you have the option to start the TeamCity Server by itself or with one default build agent.  See the [documentation](https://confluence.jetbrains.com/display/TCD9/Installing+and+Configuring+the+TeamCity+Server#InstallingandConfiguringtheTeamCityServer-StartingTeamCityserver) for details.


## Help

[TeamCity 9.x Documentation](https://confluence.jetbrains.com/display/TCD9/)

[TeamCity Licensing Information](https://www.jetbrains.com/teamcity/buy/)

Website: https://www.jetbrains.com/teamcity/
