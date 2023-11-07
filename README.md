# APK Audit Video Streaming
Android APK app audits for URL and hostname security. Reverse engineering just for fun only.

This project is for Video Streaming type apps only.

## Why Audit?
App builders cannot be trusted to use best practice when handling private data.

We audit the internal URLs so that; -
* we can check to see how strong the connection is
* we can check for any ad servers with bad connections

## Method
I only do this for fun in my spare time. I use a simple method in the below order.
* Install "App APK Extractor & Analyzer"
* Use the above to get the APK of your target
* Use d2j-dex2jar.sh to get the App.jar file
* Download and install jd-gui-1.6.6.deb into your system
* Use JD Gui to search for http:// and https:// 
* Use Shodan and other recon tools to check server security
* Use virus total to check server usage type
* Document and upload CSV to github

## Example CSV Scrape
```
cat 7Plus-URLs | grep AD, | cut -d , -f 3
```
Get only ad hostnames for ad blocker curation.

```
cat 7Plus-URLs | grep TLS1.2 | cut -d , f 3
```
Get hostnames with old TLS because we are strict.

