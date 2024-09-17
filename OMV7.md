
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
- username - `admin`
- password - `openmediavault`

## Update the admin password
1. Click on the `user settings` (in the top right corner, a symbol of human).
2. Select `change password`
3. Enter new password.
4. Confirm new password.
5. Save the new password
6. Click on the `user settings` (in the top right corner, a symbol of human).
7. Click on `log out`
8. enter with your new username and password.

## wipe HDD (optinoal)
1. Connect the HDD to the raspberry pi
2. Click on `Storage` (on the left side menu)
3. Click on `Disks`
4. select the HDD (for example /dev/sda).
5. Click on the wipe (icon at the top of the disks list that looks lik eraser).
6. select the `Confirm` checkbox.
7. Select `Yes`
8. Click `Secure`
9. Wait until the wipe is finished (it could take long time if the device is big)
10. After it finish, click `close`

## Format HDD (optinal)
1. Connect the HDD to the raspberry pi.
2. Click on `Storage` (on the left side menu)
3. Click on `File systems`
4. Click on create file system  (icon at the top of the disks list that looks like plus sign).
5. Choose `EXT4`
6. Choose the HDD.
7. Click `Save`
8. Wait until the file system will be created.
9. Click on close
10. Select the file system of the hdd
11. click `Save`

## Mount HDD
1. Connect the HDD to the raspberry pi.
2. Click on `Storage` (on the left side menu)
3. Click on `File systems`
4. Click on mount file system  (icon at the top of the disks list that looks like play sign).
5. Select the file system of the hdd
6.  click `Save`

## Enable docker
1. Click `System`
2. Click `omv-extras`
3. Check the docker repo
4. Click `save`
5. Click apply pending configurations changes.
6. Click `plugins` and the side bar.
7. search docker
8. install the compose plugin
9. install the scripts plugin.
