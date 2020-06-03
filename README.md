# appdContainerized
Steps to run
- Docker environment - these instruction assume you have a recent Docker engine running and have all the permissions to run a container on it, as well as have docker-compose configured
- You have downloaded the AppDynamics Platform install from https://download.appdynamics.com/download/. Specifically the "Enterprise Console - 64-bit linux (sh)"
- Clone this project onto the server that is hosting the Docker engine
- Open up the file "platform-solo/docker-compose.yml" and make the following changes:
  - Under "platform->hostname", change the value to match the hostname of the host docker is running on. Please keep in mind, it is required by AppDynamics to have a hostname, so an IP or "localhost" won't do.
- Open up the file "platform-solo/response.varfile" and make the following changes:
  - Set the serverHostName to the hostname of the Docker host.
  - Change any password variables defined; there should be two: platformAdmin.databaseRootPassword, platformAdmin.adminPassword
  - Change platformAdmin.useHttps$Boolean value to true or false, depending on whether you need to use HTTPS
- Change directory to "platform-solo"
- Run "docker-compose ." You should now see the container start. It will take a while for the install to finish, but you should be able to continue once you see the line "Finishing installation ..."
- Open a browser and go to "<hostname>:9191" and log into the Enterprice Console
- From here, you should be able to perform a same server, single instance of the Platform into the container. DO NOT change the installion directory as that is a location that has been created earlier and changing the location could result in a failure to install.
