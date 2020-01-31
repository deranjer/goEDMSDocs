+++
title = "Basics"
date = 2020-01-30T22:43:47-05:00
weight = 5
+++

### The Basics

EDMS stands for Electronic Document Management System.  Essentially this is used to scan and organize all of your documents.  OCR is used to extract the text from PDF's, Images, or other formats that we cannot natively get text from.

goEDMS is an EDMS server for home users to scan in receipts/documents and search all the text in them.  The main focus of goEDMS is simplicity (to setup and use) as well as speed and reliability.  Less importance is placed on having very advanced features.

goEDMS consists of two elements, the frontend and the backend.  The backend is written in Golang with the Echo framework.  It has a REST API that I plan on cleaning up and releasing at some point in the future.  This will allow you to write a different frontend or at least send commands to the backend directly.

The frontend is written in React and communicates with the backend via the REST API. The frontend is served directly by the Echo framework (on the same port as the backend), but perhaps in the future that can be configured to not launch the frontend automatically so you can swap your own frontend in.

### Whats included

Currently goEDMS is in alpha development and has some basic features and document types it supports.  The plan is to hopefully add more later.  The current supported (but not all of them are actually tested) formats are:

* pdf
* tiff
* jpg
* jpeg
* png

OCR is provided by tesseract (required) and conversion/cleanup is done by imagemagick (required).  These are free to install and use, and most EDMS solutions for home use them.

The frontend can display, delete, upload and download documents.  Currenty moving documents (via any method) is not supported (and will fatally error out the backend server), but hopefully plan to add that in the future.