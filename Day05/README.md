# Day 05: Data Visualization with Google Charts

> Not the page you want to view? [Back to home page](../README.md)

In this theory session, we will be going through the data visualization options. We will learn:

* Introduction to data visualization
* Choosing the right visualization technique
* Overview of Google Maps Platform
* Embedding Google Charts in your website using `<iframe>`

Some details about the event can be found in the [Event Page](https://gdsc.community.dev/events/details/developer-student-clubs-university-of-malaya-presents-gcpe-google-cloud-platform-for-everyone-workshop-2023-2023-04-02/). Below are some of the useful links that are relevant to the theory today.

* [Keynote](./assets/slide.pdf) by [Lim Jun Yi](https://github.com/LimJY03) and [Lim Jack Sheng](https://github.com/Jacksheng127).
* [Slido Q&A Link](https://app.sli.do/event/g23hjs7CXoJ316W6JDpaNp/live/questions?clusterId=eu1)
* [Google Charts](https://developers.google.com/chart)
* [Looker](https://www.looker.com/)

---

## Hands-On: Embedding Google Charts in Your Website

This manual is written by [Lim Jack Sheng](https://github.com/Jacksheng127), edited by by [Lim Jun Yi](https://github.com/LimJY03).

> In the workshop today, we will create a embed our Google Charts in the website.

You can alternatively refer to <!--[these videos]()--> and follow along at your own pace.

### Step 01: Download Relevant Files *(Optional)*

Download the sample website source code from [this repo](https://github.com/GCPE2023/DataVisualization). To download it, click on the green "Code" button and click "Download ZIP", or you can:

```sh
# Only if you have Git installed
git clone https://github.com/GCPE2023/DataVisualization.git
```

### Step 02: Open Receipts Data Google Sheets

Open your Receipts Data Google Sheets and paste the data from [this Google Sheets](https://docs.google.com/spreadsheets/d/1KslReSCAfiw4G2UqSPaeYqKIUWBT18Bx6hdT0uEBgeI/edit?usp=drivesdk) to your Google Sheets.

*If you don't have the Receipts Data Google Sheets, kindly create a new Google Sheets before doing the steps above.*

```diff
- Developing in progress ...
```

### Step 03: Creating Your First Line Chart

```diff
- Developing in progress ...
```

### Step 04: Creating Embed URL

Now, we change the `edit#` of the URL for the google sheet link with the following:

```
htmlembed/sheet?
```

And it should become something like:

* https://docs.google.com/spreadsheets/d/1EaAYaowfZzIWh3OvgvannRP5TnXGyBTvWrXJwBF-X_Q/**htmlembed/sheet?**gid=0

<!-- Then, we select a blank cell, don’t double click it, just click 1 times on that empty cell, you will see a blue border around that cell

Now, we click on the chart and then "`CTRL + X`" (Windows OS) or "`CMD + X`" (Mac OS) or "`CUT`" to cut it out then paste it inside the blue border blank cell

So, this mean that we have successfully paste the chart inside that cell. -->

According to the blank cell that we just select, we can add the following at the end of the link:

```
&range=<YOUR_CELL_NUMBER>
```

And it should become something like:

* https://docs.google.com/spreadsheets/d/1EaAYaowfZzIWh3OvgvannRP5TnXGyBTvWrXJwBF-X_Q/htmlembed/sheet?gid=0**&range=c7**

### Step 05: Embedding Chart Using `<iframe>`

```diff
- Developing in progress ...
```

### Step 06: Clean Up

```diff
- Developing in progress ...
```

### Complete!

You have successfully visualize your receipt data with Google Charts and embedded it in your website.

### More Readings

* 
