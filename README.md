![Balena Server Logo](images/logo.png)

# Dynu-dns
**Starter project enabling you a Dynu-dns.**

This project has been tested on a Raspberry Pi 4 B 4GB

## Hardware required

* Raspberry Pi 4B (We recommend the 4GB or the 8GB model. 1GB is not enough!) or Nvidia Jetson Nano
* A fan or cooling system to prevent lag caused by throttling
* A 16GB or greater micro SD Card (We always recommend SanDisk Extreme Pro SD cards)
* Power supply

## Software required

* A download of this project (of course)
* Software to flash an SD card ([balenaEtcher](https://balena.io/etcher))
* A free [balenaCloud](https://balena.io/cloud) account
* The [balena CLI tools](https://github.com/balena-io/balena-cli/blob/master/INSTALL.md)

## Setup and use :stars:

To run this project is as simple as deploying it to a balenaCloud application; no additional configuration is required.

### Setup the device :cd:

* Sign up for or login to the [balenaCloud dashboard](https://dashboard.balena-cloud.com)
* Create an application, selecting the correct device type for your Raspberry Pi
* Add a device to the application, enabling you to download the OS
* Flash the downloaded OS to your SD card with [balenaEtcher](https://balena.io/etcher)
* Power up the board and check it's online in the dashboard

### One Click Deployment

You can deploy this server with one click with the button below. Or, you can follow the manual deployment instructions in the next section.

[![](https://balena.io/deploy.svg)](https://dashboard.balena-cloud.com/deploy?repoUrl=https://github.com/AhsenBaig-forks/balena-ddclient)

### Manually Deploy this application :airplane:

* Install the [balena CLI tools](https://github.com/balena-io/balena-cli/blob/master/INSTALL.md)
* Login with `balena login`
* Download this project and from the project directory run `balena push <appName>` where `<appName>` is the name you gave your balenaCloud application in the first step.

## Connect to the server :satellite:

Balena dynu-dns Server sets automatically your Server hostname to `dynudns.local`. It is the address the from your server. You can connect to it like this:

**Note:** The IP address also works.

Now you have a balenaServer :sunglasses::

## Connect to the terminal :satellite:

The server has no console input option in the cloud dashboard, so you need `RCON`. The port is `25575` and the password is `balena`. It is a protocol for connecting to the server.
There are many clients, but you can pick one here:

## Connect to the file-directory :satellite:

You can connect to the server and change your serverfiles. I recommend using a tool like [WinSCP](https://winscp.net/) or if you are using OSX or a linux distribution you can use [Filezilla](https://filezilla-project.org/).  The IP Address to connect to is “dynudns” (without the quotes), the protocol to choose is SCP (If you got the choice), the port number is 22, the username is “root” (again, without the quotes) and the password is “balena” (no quotes). The files are in the folder named “serverfiles” at the root directory, you can double click to open that directory and browse the files in there.

**NOTE:** You can also change your SCP password by setting the `SCP_PASSWORD` Environment Variable within balenaCloud.  On the left, simply click on “Device Variables” and then click the “Add Variable” button. Give it a name of `SCP_PASSWORD`, and set the value to your password. 

## Change hostname
You can change the hostname by defining the DEVICE_HOSTNAME Environment Variable within balenaCloud.

**NOTE:** If you decide to change the hostname, you will have to use your new hostname within dynudns to connect to the server, instead of `dynudns.local`.

## Custom RAM (optional) :link:

Devices like the Raspberry Pi 4B 4GB or the 8GB model have enough RAM to run the server with more RAM (the default value used by balena dynudns server is 1GB). If you set `RAM` to a value like `2G`, `4G`, or `6G` it will have the specified amount of RAM available.