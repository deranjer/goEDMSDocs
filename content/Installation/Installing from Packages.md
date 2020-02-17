+++
title = "Installing from Packages"
date = 2020-01-30T22:43:47-05:00
weight = 5
+++


### Installing from Packages

#### Requirements

* imagemagick
* tesseract-ocr

{{% notice tip %}}
The listed package names are the debian package names, they may be named different for your distribution.  An installer/package is not available for Windows currently.
{{% /notice %}}

The preferred method for installation is to install the dependencies first, then the .deb/.rpm.  

{{% notice warning %}}
The .deb/.rpm packages assume you are using systemd as an init system as they install a systemd init file for goEDMS
{{% /notice %}}

So an example install would go as follows:

```shell
sudo apt-get install tesseract-ocr imagemagick
dpkg -i goEDMS-version.deb
```

The default install path for goEDMS is `/opt/goEDMS`.

After install goEDMS should automatically start.  However, most likely you will want to edit the `serverConfig.toml` (located in `/opt/goEDMS`) with your specific settings.  So you can stop goEDMS `systemctl stop goEDMS`, then edit the `serverConfig.toml` and then start goEDMS (`systemctl start goEDMS`).  The initial startup log will appear in syslog, (or view the systemctl log), but after that the log will appear in `goedms.log`, located in `/opt/goEDMS/`.
