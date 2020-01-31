+++
title = "Installing Manually/From Archive"
date = 2020-01-30T22:43:47-05:00
weight = 6
+++



### Installing from Compressed Archive

This is the only option for Windows currently, and is also available for Linux and MacOS.

#### Requirements

* imagemagick
* tesseract-ocr

For linux install the above packages from your package manager, they should be available for most distributions, although those are the debian package names, they might be named different for your distro.  For Windows download the installers for both programs and install them in your preferred location.

#### Recommended Steps

* Make Directory for goEDMS
* Extract the archive at the root of the directory
* Ensure the goEDMS binary is marked as executable
* Make user specifically to run goEDMS
* Make the user owner of the goEDMS directory
* Modify the ServerConfig.toml file to reflect your desired settings
* Add goEDMS to your init system (a systemd start file is included in the repo in "dist-specific-files\Linux-systemd")
* Run the goEDMS binary manually to watch for errors
* Check the goedms.log file for errors if it starts successfully
* Start goEDMS via your init system
