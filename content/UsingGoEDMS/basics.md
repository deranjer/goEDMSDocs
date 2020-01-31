+++
title = "The Basics"
date = 2020-01-30T22:43:47-05:00
weight = 5
+++

### The Basic Flow

#### Adding Documents

Adding documents is currently supported via two methods.  The first is by placing them in the "ingress" folder.  The backend periodically scans the folder and adds any documents placed in that folder.  The other method is by uploading them from the web interface.  I hope to add a few more methods at some point.

#### Searching Documents

On the react frontend there is a search box, enter your search term there.  Currently goEDMS only does a "loose" search which matches that term in any configuration/file it finds and returns all the documents that contain that term.  I hope to add more search options soon.

#### Managing Documents

All document management currently MUST be done from the frontend. Currently any mismatch in what the database expects vs what it finds will cause a fatal error.  I hope to make it much more resilient in the future.  From the frontend you can upload documents, delete documents, view documents and download documents.

#### Files

| File Name | Description |
| --------- | ----------- |
| goEDMS.db | This stores all the information about the documents, like their location, name, upload time, direct URL, ULID (similar to UUID), hash, and OCR results |
| simpleEDMSIndex.bleve | This is a folder/database that contains the optimized index for searching all OCR results |
| serverConfig.toml | Stores all of the configuration options for goEDMS |
| goedms.log | Log file for goEDMS |
| public/built | Folder that contains the react frontend. `frontend-config.js` is the only file that should be of interest to you, that contains the URL that the frontend uses to connect to the backend.  It should be automatically generated when goEDMS configures on startup. |
| documents | Contains your document database.  This should not be manually edited |
| done | Ingressed documents are moved here after processing.  You CAN delete these without messing up goEDMS, but make sure they are backed up |
| ingress | goEDMS searches this file periodically for new documents to scan |
| temp | goEDMS writes and image here as needed to OCR documents |
