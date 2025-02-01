# Protected image worker :key:
This project is a Cloudflare Worker that serves password-protected images, This project leverages Cloudflare’s edge network, ensuring fast and secure delivery without the need for a traditional backend server.

# Features :white_check_mark:
- simple image viewer
- password protection
- serverless
- image converted to base64

# How to setup :envelope_with_arrow:
### cf
1. download the `worker.js` file from this repository
2. go to [Cloudflare](https://dash.cloudflare.com/sign-up) website and signup/login
3. on the sidebar find ``worker and pages``, choose `create` and write a name for your worker then click on `deploy`
4. click on `Edit code`, and delete the default code (hello world js codes)
5. right-click and choose `upload` and upload the `worker.js` file you downloaded, then click on `deploy` and wait for the version saved notification
### covers
1. go to [base64 image](https://www.base64-image.de/) website
2. for conversion, upload your photo and wait for converting, then click on show code
3. after a few minutes, it shows you a code like (data:image/png;base64,iVBORw0KGgoAA......), save it and go to next part
### adding
1. on the sidebar look for Storage & Databases and choose KV
2. create a **KV** with a name you want then choose it and go to KV pairs tab
3. fill the **key** input with this `image` (key= image), for **value** fill the part with the base64 code you saved then click on `add entry`
### bks
1. back to your worker 
