# Day 02: Website Building and Hosting

> Not the page you want to view? [Back to home page](../README.md)

In this theory session, we will be going through the basics of website development. We will learn:

* Introduction to HTML and CSS
* Introduction to Web Hosting

Some details about the event can be found in the [Event Page](https://gdsc.community.dev/events/details/developer-student-clubs-university-of-malaya-presents-gcpe-google-cloud-platform-for-everyone-workshop-2023-2023-03-19/). Below are some of the useful links that are relevant to the theory today.

* [Keynote](./assets/slide.pdf) by [Dominic Chong Rong Yau](https://github.com/dominicchong) and Peh Kyung Kit.
* [Slido Q&A Link](https://app.sli.do/event/ip3RAVqsNXxdr6V9fMoHJz/live/questions)
* [Online HTML Editor](https://www.tutorialspoint.com/online_html_editor.php)

---

## Hands-On: Host your Website on Firebase

This manual is written by [Dominic Chong Rong Yau](https://github.com/dominicchong), edited by by [Lim Jun Yi](https://github.com/LimJY03).

> In the workshop today, we will host our website on Firebase.

### Step 01: Install Firebase CLI

We will start by installing the Firebase CLI (Command Line Interface) from [this link](https://firebase.google.com/docs/cli).

### Step 02: Login to Firebase Website

We will now go to the [Firebase website](https://firebase.google.com/). Log in with the account that you used to activate Free Trial on Google Cloud Platform.

Then, create a new project by clicking "Get Started" > "Create a Project". Name your project with a **unique** name.

### Step 03: Download website template

Download the website template from [this GitHub repo](https://github.com/GCPE2023/GCPE2023-Website). To download it, click on the green "Code" button and click "Download ZIP", or you can:

```sh
# Only if you have Git installed
git clone https://github.com/GCPE2023/GCPE2023-Website.git
```

### Step 04: Modify the website content

Unzip the downloaded ZIP file if you chose to "Download ZIP" in the previous step, then navigate to "finished" > "public". In this step, we will be replacing the `profile.jpg` with your own image renamed `profile.jpg`. If your image has different name or different file extension (ie `png` or `webp` etc.), you can modify the code in **Line 33** of the `index.html` file to modify the image path.

```html
<img src="./<YOUR_FILE_NAME.EXTENSION>" alt="profile picture">
```

Change the `<YOUR_FILE_NAME.EXTENSION>` to the file name of your image. For instance, if your file name is `myprofile.png` then change **Line 33** of the `index.html` file to the following:

```html
<img src="./myprofile.png" alt="profile picture">
```

### Step 05: Login to Firebase through CLI

Open up your Firebase CLI, type the following into the CLI terminal:

```sh
firebase login
```

This will let your Firebase CLI have access to the projects in your account.

> **Note**
> <br>If this is your first time logging into the Firebase through CLI, it will open up a new window for you to choose your account to sign in to Firebase.

Then, we will navigate to our `finished` folder in the Firebase CLI. We will perform the `cd` command to change the directory of the CLI. We will need to copy the folder path for this step, type the following command in the CLI and replace the `<FOLDER_PATH>` with your copied folder path:

```sh
cd <FOLDER_PATH>
```

> **Note**
> <br>You can copy your folder path by right-clicking on the folder and click "Copy Path"

We can type `dir` (for Windows) or `ls` (for LinuxOS and MacOS) in the Firebase CLI to look at the files in our directory. The only folder inside should be the `public` folder.

### Step 06: Initializing Firebase Hosting

Now we will initialize our Firebase project on our set directory by typing the command below:

```sh
firebase init hosting
```

We will choose "Use an existing project" because we have already created the project in Firebase website. For the "Hosting Setup", we will put `public`, `Yes`, `No`, `No` for the next 4 prompts in the Firebase CLI. What we've done is:

* `public`: we set the `public` folder as the Public directory accessible anywhere online.
* `Yes`: all requests to non-existence urls or files for our web application will be directed to `index.html` page. Learn more in [Firebase Documentation](https://firebase.google.com/docs/hosting/full-config#rewrites).
* `No`: since our file is deployed locally instead of directly from GitHub, we do not need this option.
* `No`: we don't need to overwrite our available `index.html` page with the firebase generated file.

In this part, few files will be created in the `finished` folder:

* `firebase.json`
* `.firebaserc`

### Step 07: Deploy to Firebase

Finally, we will deploy our website to Firebase server with the following command:

```sh
firebase deploy
```

We can make further changes to our website locally and when we are ready to push the updates to firebase, we will redeploy by typing the command above again in Firebase CLI.

> **Note**
> <br>If refreshing the tab does not show any changes, press "ctrl+shift+R" (for Windows) or "cmd+shift+R" (for MacOS) to force reload and clear the browser cache.

### Step 08: Clean Up

Open back your Firebase website, select your project and at the left panel, click the `settings` icon and the Project Settings page should open. Under the `general` tab, scroll to the bottom and click "Delete Project". However, we will be upgrading the current website with implementation of more features

### Complete!

You have successfully hosted your own website on Firebase server!

### More Readings

* [Hostinger Web Hosting](https://www.hostinger.com)
* [Bluehost Web Hosting](https://www.bluehost.com/?utm_campaign=affiliate-link_searchbrandpromo_PPC&utm_source=direct&utm_medium=affiliate&utm_affiliate=searchbrandpromo&irpid=100&clickid=P99C100S570N0B5578A2D4499E0000V119&pb=signup_searchbrandpromo&channelid=P99C100S570N0B5578A2D4499E0000V119&utm_source=google&utm_medium=brandsearch&gclid=EAIaIQobChMI3YeZ5aHn_QIV0QRyCh30rw7mEAAYASAAEgKR7PD_BwE&gclsrc=aw.ds)
* [Google Cloud Web Hosting](https://cloud.google.com/solutions/web-hosting/?utm_source=google&utm_medium=cpc&utm_campaign=japac-MY-all-en-dr-SKWS-all-hv-trial-EXA-dr-1605216&utm_content=text-ad-none-none-DEV_c-CRE_624245403111-ADGP_Hybrid%20%7C%20SKWS%20-%20EXA%20%7C%20Txt%20~%20Application%20Modernization_Web%20Hosting_web%20hosting_main-KWID_43700073339911746-kwd-10085951&userloc_9066745-network_g&utm_term=KW_web%20host&gclid=EAIaIQobChMIo4--0p7n_QIV0ZlmAh0VXgT8EAAYASAAEgJdgfD_BwE&gclsrc=aw.ds)
