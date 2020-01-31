+++
title = "The Server Config File"
date = 2020-01-30T22:43:47-05:00
weight = 6
+++

### The Basics

The `serverConfig.toml` file is what stores all of the configuration for goEDMS.  It can be either placed in the same directory as the binary file, or in a folder named `config` that is in the same directory as the binary.  The `serverConfig.toml` file should have basic documentation in it on what the various settings do, that will be added here and maybe some more explanation.

#### serverConfig

| Section | Option | Description | Input Format | Notes |
| ------- | ------ | ----------- | ------------ | ----- |
| serverConfig | ServerPort | Required to input as string | String | This is the port you want the server to bind to. |
| serverConfig | ServerAddr | Put in the IP address you want to bind to as string, if blank will bind to all available addresses | String | None |
| serverConfig | APIURL | This is for EXTREME edge cases where you want to manually force the API URL, like with Docker, usually leave blank | String | In format (usually, unless running behind proxy) `http://192.168.1.10:8000` |
| documentLibrary | DocumentFileSystemLocation | Location to store documents | String | Relative or absolute path accepted, the server will convert any relative path to an absolute path. |
| documentLibrary | DefaultNewDocumentFolder | default folder that ingressed documents will be placed in (inside the Document library), for multiple folders deep can do '2020/New' | String | If `PreserveDirStructure` is set to false all files will go in the `New` folder, if it is true, the New folder will be created but not used. |
| ingress | IngressPath | default path that the server will scan for new documents | String | Can be absolute or relative |
| ingress.scheduling | IngressInterval | number of minutes between scans of the ingress folder | Integer | None |
| ingress.completed | IngressDeleteOnProcess | #If True will delete files from ingress folder after processed (will leave ones if they produce error), if false will move to another folder | Boolean | Will move it to folder "done" by default |
| ingress.completed | IngressMoveFolder | default path that the server will move processed ingress documents to | String | None |
| ingress.handling | PreserveDirStructure | if nested folders are in the ingress path will copy that existing structure to document storage | Boolean | None |
| ocr | TesseractBin | #Path to Tesseract binary (required for OCR) #Windows paths need to be formatted as such: `C:\\Program Files\\Tesseract-OCR\\tesseract.exe` | String | Common linux path is `"/usr/bin/tesseract"`
| ocr | MagickBin | Path to ImageMagick (required for OCR) | String | IMPORTANT For linux, the MagickBin command needs to be to the "convert" binary, for Windows it is "magick.exe" |
| authentication | CURRENTLY NOT IMPLEMENTED | None | None |
| reverseProxy | ProxyEnabled | This is for setting up goEDMS behind a reverse Proxy (with SSL), as a subdomain route (https://goedms.domain.com) | String | None |
| reverseProxy | BaseURL | URL is CASE SENSITIVE # MUST be in the subdomain format, NO trailing slash (suburl proxy does not work, i.e. https://domain.com/goedms) | String | None |
| frontend | NewDocumentNumber | CURRENTLY NOT IMPLEMENTED | None | None |
| logging | Level | debug, info, warn, error, fatal | String | Only accepts the description values, nothing else |
| logging | OutputPath | file or stdout | String | Only accepts "file" or "stdout" stdout just outputs it to the shell or syslog |
| logging | LogFileLocation | Location of Log file (if file selected for OutputPath) | String | None |
| notifications | PushBulletToken | CURRENTLY NOT IMPLEMENTED | None | None |
