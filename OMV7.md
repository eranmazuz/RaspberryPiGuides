# Installing OMV7 on a Raspberry PI

## Introduction

Installing OMV7 on Raspberry PI 5 OS Lite, using a scripted install.

## Prerequisites
- Raspberry pi 5
- Raspberry PI OS Lite 64 bit

|**Warning**|
|--|
|The user can't be called admin because that user will be used in the OMV 7|

|**Warning**|
|--|
|Use wired internet first because the OMV installation will reset the wifi, you can configure the wifi later in the OMV GUI|


## Preinstall

	sudo apt-get update
	sudo apt-get upgrade -y
	wget -O - https://github.com/OpenMediaVault-Plugin-Developers/installScript/raw/master/preinstall | sudo bash
	sudo reboot

## Install
	wget -O - https://github.com/OpenMediaVault-Plugin-Developers/installScript/raw/master/install | sudo bash

## Login
Enter the url of the raspberry pi `http://[pi name].local`
In the login enter the following:
- username - admin
- password - openmediavault
