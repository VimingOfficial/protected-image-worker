<p align="center">
  <img src="https://raw.githubusercontent.com/VimingOfficial/protected-image-worker/main/Screenshot1.png" width="500" alt="Screenshot">
</p>

# Protected image worker :key:
This project is a Cloudflare Worker that serves password-protected images, This project leverages Cloudflare’s edge network, ensuring fast and secure delivery without the need for a traditional backend server.

# Features :white_check_mark:
- simple image viewer
- password protection
- serverless
- image converted to base64

# How to setup (5 minutes needed) :envelope_with_arrow:
### Setting up the Cloudflare worker code
1. download the `worker.js` file from this repository
2. go to [Cloudflare](https://dash.cloudflare.com/sign-up) website and signup/login
3. on the sidebar find ***worker and pages***, choose ***create*** and write a name for your worker then click on ***deploy***
4. click on ***Edit code***, and delete the default code (hello world js codes)
5. right-click and choose ***upload*** and upload the `worker.js` file you downloaded, then click on ***deploy*** and wait for the version saved notification
### Converting the image from png to base64 code
1. go to [base64 image](https://www.base64-image.de/) website
2. for conversion, upload your photo and wait for converting, then click on show code
3. after a few minutes, it shows you a code like (data:image/png;base64,iVBORw0KGgoAA......), save it, and go to the next part
> ⚠️ **NOTE:**
> Base64 code is a long code, so make sure you save it completely
### Creating KV for image data
1. on the sidebar look for ***Storage & Databases*** and choose ***KV***
2. create a **KV** with a name you want then choose it and go to ***KV pairs*** tab
3. fill the `key` input with this `image` (key= image), for `value` fill the part with the `base64 code` you saved then click on ***add entry***
> 🚨 **IMPORTANT:**
> key=image   and   value=data:"YOUR-BASE64-CODE"
### Final setup (password and data)
1. back to your worker page and go to the ***settings*** tab
2. go to the ***Bindings*** part and click on Add then choose KV namespace, you should fill `Variable name` with `Data` , and on the `KV namespace` choose the `KV` you made from the list then deploy
> 🚨 **IMPORTANT:**
> Variable name=Data   and   KV namespace="YOUR-KV-NAME"
4. for setting a password, go to ***Variables and Secrets*** part and fill the `Variable name` with `PASSWORD` then fill the `Value` with `your own password`
> 🚨 **IMPORTANT:**
> Variable name=PASSWORD   and   KV namespace="YOUR-PASSWORD"

   ***Done, open the link and use***
