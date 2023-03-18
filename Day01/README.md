# Day 01: Introduction to Google Cloud

In this theory session, we will be going through the introduction to cloud computing and Google Cloud as a whole. We will learn:

* The history of cloud
* IaaS, PaaS and SaaS
* Google Cloud services
* Cloud Digital Leaders

Some details about the event can be found in the [Event Page](https://gdsc.community.dev/events/details/developer-student-clubs-university-of-malaya-presents-gcpe-google-cloud-platform-for-everyone-workshop-2023-2023-03-18/). Below are some of the useful links that are relevant to the theory today.

* [Keynote](./assets/Introduction-to-Google-Cloud.pdf) by [Lim Jun Yi](https://github.com/LimJY03) and Lim Jack Sheng.
* [Google Cloud services and products](https://cloud.google.com/products)
* [Cloud Digital Leaders learning path](https://cloud.google.com/certification/cloud-digital-leader)

---

## Hands-On: Host your own Minecraft server

This manual is written by [Lee Weng Hong](https://github.com/AsynchronousNotAvailable) and [Ariq Ramdhany](https://github.com/ramdhanyA).

> In the workshop today, we will host our own Minecraft server on a Google Cloud VM Instance.

### Step 01: Install `server.zip` file

The `server.zip` file can be downloaded in [this link](https://drive.google.com/file/d/1ZWcqk4kx4qZZNx29v-qSBPull9YHCoPQ/view). Download it to a local directory in your computer and remember where the directory.

> **Note**
> <br>The video tutorial can be found [here](https://drive.google.com/file/d/1hpJDs59mpguvUomvkp3qSjBgMGutGLLk/view).

### Step 02: Setup GCP free trial account

```diff
- Developing in progress ...
```

> **Note**
> <br>If you encounter errors, try using different account (non organizational account), or different cards.

### Step 03: Enable Compute Engine API

```diff
- Developing in progress ...
```

### Step 04: Setting up firewall rule

```diff
- Developing in progress ...
```

### Step 05: Creating a VM

```diff
- Developing in progress ...
```

### Step 06: Uploading `server.zip` file to VM

```diff
- Developing in progress ...
```

### Step 07: Setting up VM environment

```diff
- Developing in progress ...
```

### Step 08: Unzipping `server.zip`

In your SSH terminal, type the following code to unzip the `server.zip` file:

```sh
unzip server.zip
```

After the file completes unzipping, you can type the following to see the files in the current directory:

```sh
ls
```

Now you should see there is a `server` beside the `server.zip`. Navigate into the `server` folder with the following command:

```sh
cd server
```

`cd` stands for Change Directory. So, now we already changed our directory to the server folder. Let's look at the content in the folder:

```sh
ls
```

You should be able to see a `server.jar` file in the output.

### Step 09: Start a Minecraft server

We will start the Minecraft server by typing the following command in the SSH terminal:

```sh
java -jar server.jar
```

Many lines of logs will be shown, after a few minutes, the server will be started. You can try and type the following command in the SSH terminal to see the condition of the server:


```sh
tps
```

This shows the [Tick Per Second](https://minecraft.fandom.com/el/wiki/Tick) of the Minecraft server. A TPS of 20.0 will be ideal. Now you can go back to the VM Instance page and copy the external IP address. That IP address will be the IP for your Minecraft server.

In your Minecraft multiplayer tab, you can choose `Join a Server` or `Direct Connection` and paste your external IP address in the `IP Address` box. Then you should be able to join the Minecraft server.

### Step 10: Clean up

To stop the Minecraft server, you can just close the SSH terminal window or type the following command in the SSH terminal:

```sh
stop
```

In the VM Instances page, you can click on the `dropdown` icon beside the "SSH" button and click "Delete VM".

### Complete!

You have successfully hosted your own Minecraft server!

### More Readings

* [What is Google Cloud VM Instance](https://cloud.google.com/compute/docs/instances#introduction)
* [Applications of VM Instance](https://cloud.google.com/learn/what-is-a-virtual-machine)
* [Using Google Cloud VPC Firewall](https://cloud.google.com/vpc/docs/using-firewalls)
* [Learn GCP by setting up a Minecraft server](https://cloud.google.com/blog/products/management-tools/brick-by-brick-learn-gcp-by-setting-up-a-minecraft-server#:~:text=With%20Cloud%20Functions%20you%20can,and%20stop%2Dminecraft%2Dserver%20.)
* [Hosting Minecraft on Google Cloud with Automatic Backup](https://medium.com/@manbobo2012/host-a-minecraft-server-on-google-cloud-with-automatic-deployment-and-backup-f00d49a1a306)
* [Aternos (Alternative Platform to host your Minecraft Server for FREE)](https://aternos.org/:en/)
* [Hosting Minecraft server on your local computer](https://help.minecraft.net/hc/en-us/articles/360058525452-How-to-Setup-a-Minecraft-Java-Edition-Server)
