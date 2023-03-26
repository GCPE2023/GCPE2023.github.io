# Day 04: Integrating AI in Your Website

> Not the page you want to view? [Back to home page](../README.md)

In this theory session, we will be going through the application of AI. We will learn:

* Storage options on Google Cloud
* Vision API on Google Cloud
* JSON Object

Some details about the event can be found in the [Event Page](https://gdsc.community.dev/events/details/developer-student-clubs-university-of-malaya-presents-gcpe-google-cloud-platform-for-everyone-workshop-2023-2023-03-26/). Below are some of the useful links that are relevant to the theory today.

* Keynote by [Lim Hui Ern](https://github.com/huiern214) and [Vanessa Jing Taing](https://github.com/Vanessa-Taing)
* [Slido Q&A Link](https://app.sli.do/event/7KBiwvEjSCK3agsmE6yBvJ/live/questions)
* [Google Cloud Storage Options](https://cloud.google.com/products/storage)
* [What is Vision API](https://cloud.google.com/vision)
* [Understanding JSON](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/JSON)

---

## Hands-On: Extracting Receipt Data

This manual is written by [Lim Hui Ern](https://github.com/huiern214) and [Vanessa Jing Taing](https://github.com/Vanessa-Taing), edited by by [Lim Jun Yi](https://github.com/LimJY03).

> In the workshop today, we will create a Receipt Data Extractor.

You can alternatively refer to <!--[these videos]()--> and follow along at your own pace.

### Step 01: Download Relevant Files

Download the sample receipts and Python code from [this repo](https://github.com/GCPE2023/GCPE-ReceiptExtractor). To download it, click on the green "Code" button and click "Download ZIP", or you can:

```sh
# Only if you have Git installed
git clone https://github.com/GCPE2023/GCPE-ReceiptExtractor.git
```

### Step 02: Uploading Receipts to Google Drive

```diff
- Developing in progress ...
```

### Step 03: Creating Cloud Bucket

```diff
- Developing in progress ...
```

### Step 04: Enabling Relevant APIs

```diff
- Developing in progress ...
```

### Step 05: Authorizing APIs

```diff
- Developing in progress ...
```

or alternatively, you could use the `gcloud` command in the Cloud Shell with the following command:

```sh
gcloud services enable drive.googleapis.com vision.googleapis.com sheets.googleapis.com
```

### Step 06: Creating a new Google Sheets

```diff
- Developing in progress ...
```

### Step 07: Coding on Cloud Shell Editor

```diff
- Developing in progress ...
```

### Step 08: Clean Up

```diff
- Developing in progress ...
```

### Complete!

You have successfully extracted your receipt data in batches!

### More Readings

* [Google Cloud Vison API Documentations](https://cloud.google.com/vision/docs)