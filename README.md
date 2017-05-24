# Predix DAC Bootstrap - Utility Script

Are you interested in using Decisyon App Composer (DAC) for Predix and looking for a one-step configuration approach? Run this script to setup all you need to start using DAC.

The script creates instances on Predix for the following services: UAA, Timeseries, Asset and DAC and it configures them to provide a ready-to-use environment for DAC on Predix (necessary authorities, scopes, create a UAA user, create UAA client_id, UAA groups etc.)

For sure, it is a quick and dirty script but it should work. I know, it is not perfect. My intention was not to create a perfect piece  but a usable one.

## What is DAC?

The Decisyon App Composer (DAC) was created to rapidly construct prototypes and production applications that leverage Predix and other native microservices to inject real-time intelligence into business operations.

Build app pages in minutes using DAC's intuitive visual editor, eliminating long, laborious, and error-prone software development, test, and release cycles.

Further information available [here](https://www.predix.io/services/service.html?id=2018).

### DAC Prerequisites

Make sure to install the required prerequisites to use DAC Design Time VM:

- [Java Virtual Machine](https://java.com/en/download/)
- [Oracle VirtualBox](https://www.virtualbox.org/wiki/Downloads)
- [Vagrant](https://www.vagrantup.com/downloads.html)
- [Decisyon App Composer Starter Kit](http://decisyon.com/docs/Decisyon_App_Composer_Starter_Kit.pdf) to guide you through the design and deployment of your App Composer application to the Predix cloud.

## Prerequisites

Make sure to have the required prerequisites in place:

- A working internet connection :-)
- An account on Predix.io
- [Git](https://git-scm.com/downloads)
- [Cloud Foundry CLI](https://github.com/cloudfoundry/cli)
- [Ammonite](http://www.lihaoyi.com/Ammonite/) that lets you use the Scala language for scripting purposes.

## How to use it?

This script has been developed and tested against Scala 2.12.1 Java 1.8.0_73 on Linux (Ubuntu) and Mac OSX 10.x.

Below the steps for Linux and Mac users:

1. Configure networks and proxies
2. Execute the following steps to clone the repos and run the script

```
$ git clone https://github.com/indaco/predix-dacdemo-setup
$ cd predix-dacdemo-setup
$ amm main.sc
```

Windows users can use the DAC VM to execute the script. Below the steps:

1. Use the [Decisyon App Composer Starter Kit](http://decisyon.com/docs/Decisyon_App_Composer_Starter_Kit.pdf) to download and run the DAC Design Time VM
2. Configure networks and proxies
3. Open a terminal window on the VM
4. Execute the following steps to clone the repos and run the script

```
$ git clone https://github.com/indaco/predix-dacdemo-setup
$ cd predix-dacdemo-setup
$ amm main.sc
```
#### Notes

`src/variables.sc` file contains the default settings for the script (e.g. predix service plan, service names, instance names, client_id, user details etc.). Adapt them to your preferences.

#### Results

The scripts generates a JSON file with details about the services created. It can be used for further reference. It is exactly the output for `cf env appName` command.

## And Now?

Refer to the Use the [Decisyon App Composer Starter Kit](http://decisyon.com/docs/Decisyon_App_Composer_Starter_Kit.pdf) for a complete tutorial on how to compose and deploy an application developed with DAC on Predix.

--------------------------------------------------------------------------------

#### Known Issues

- [Pushing the sample_app to Predix could freeze the script at "starting app"](https://github.com/indaco/predix-dac-bootstrap/issues/1)

--------------------------------------------------------------------------------

#### DISCLAIMER

- This is not an official development neither from the GE Digital's Predix Team and Decisyon Team.
