# VDO.Samurai is a fork of

<img src="https://github.com/user-attachments/assets/8134f167-2ea5-42e8-9450-b7aed322b6b0" width="300" />

[![GitHub Repo stars](https://img.shields.io/github/stars/steveseguin/vdoninja?style=social)](https://github.com/steveseguin/vdoninja)
[![GitHub forks](https://img.shields.io/github/forks/steveseguin/vdoninja?style=social)](https://github.com/steveseguin/vdoninja/fork)
[![Share on Twitter](https://img.shields.io/twitter/url?style=social&url=https%3A%2F%2Fgithub.com%2Fsteveseguin%2Fvdoninja)](https://twitter.com/intent/tweet?text=Check%20out%20VDO.Ninja%20-%20Peer-to-peer%20video%20streaming%20for%20OBS%20and%20more!&url=https%3A%2F%2Fgithub.com%2Fsteveseguin%2Fvdoninja)

#### ⚠ Notice! We've rebranded from OBS.Ninja to VDO.Ninja - all else is staying the same ✨


## What is VDO.Ninja? 🚀

VDO.Ninja brings peer-to-peer technology to OBS and other studio software, enabling remote camera integration with:

* 🔒 Direct peer-to-peer video transfer in most cases
* ⚡ High-quality video with super low latency
* 💪 Director control room with group chat
* 📱 Smartphone wireless webcam capabilities
* 🌐 Supports WHIP/WHEP and self-hosted SFUs
* 🆓 Free software. Free managed services. Free support.

## What is VDO.Samurai?

VDO.Samurai is a modded version of VDO.Ninja for me and my friends to use privately.

<img src="https://user-images.githubusercontent.com/2575698/120865595-56de3b80-c55c-11eb-8b98-60c59ae0f904.png" height="300" />

## How to Use 📝

You can get started by just opening [VDOSamurai.vercel.app](https://vdosamurai.vercel.app/) in your browser and selecting *Add your Camera to OBS*.

* 🎥 [Basic Intro Video](https://www.youtube.com/watch?v=QaA_6aOP9z8&list=PLWodc2tCfAH1l_LDvEyxEqFf42hOBKqQM&index=1)
* 📺 [YouTube Video Tutorials](https://www.youtube.com/watch?v=mQ1Jdhf5aYg&list=PL8VJWj2-XLFpFu3G35Hdm1nKZ2xn9_0_8)

Join the [Discord](https://discord.vdo.ninja) for community exhibitions, discussions, support, and feature updates.


## What's in this repo
This repo contains the web client software for VDO.Ninja, along with many sample apps that leverage its IFRAME API. A sample config file and instructions for setting up an optional TURN video relay server is also provided here. The user documentation for VDO.Ninja itself is found at docs.vdo.ninja.

## How to Deploy this Repo
VDO.Samurai is available as a free-to-use hosted service at https://vdosamurai.vercel.app, so deploying is optional. If you do wish to self-deploy the service however, details are provided below.

Hosting a private/personal deployment can be as simple as hosting the files in this repository on a HTTPS-enabled webserver. For a very simple method on how to do this, there's a video guide here: https://www.youtube.com/watch?v=uYLKkX2_flY

For more advanced users, you can see the [install.md](https://github.com/detectivesheepy/vdosamurai/blob/master/install.md) file for alternative hosting options and more details on deploying additional system components. Limited technical support is provided for self-deployments, mainly due to how time-consuming such requests are, but the details to fully-deploy all required system components are provided in the install.md file. 

If self-hosting, you might also wish to host your own video relay TURN server.  Directions on how to deploy a TURN server are listed in the [turnserver.md](turnserver.md) file. Only about ~ 5% of remote guests usually will need a TURN server, often those connected via 4G LTE or those behind a strict firewall, but most other users don't need one. While VDO.Ninja does host some pubiic TURN servers, they are quite expensive to operate, so please try to avoid abusing if possible. If you are deploying your own version of VDO.Ninja, I'd ask you to use your own TURN servers if you are capable of doing so; it's understandable if you aren't able to though.

For users wishing to host VDO.Ninja offline (where no Internet is available), there's a repository with everything needed to deploy locally and offline here: https://github.com/steveseguin/offline_deployment. The offline version includes a Docker option, and there are some community-created Dockers available for online hosting. I may eventually offer an official Docker option designed for online users with heavier requirements, but I lack time and support to maintain such a project currently.

### Develop vs Release versions

The develop branch of this repo is a bit like the preview or nightly version of VDO.Ninja. It's intended to be functional, but it may not be that well tested, or there could be incomplete features. The develop version aligns closely with what is normally on vdo.ninja/alpha/, which is well suited for those wishing to submit code changes or to gain access to experimental new features. You can access a hosted version of the GitHub develop branch on Github pages here as well: https://steveseguin.github.io/vdo.ninja/

Release versions of VDO.Ninja have their own branches though. These latest release branch will be updated to fix bugs or critical issues as needed, but are otherwise unchanged. https://github.com/steveseguin/vdo.ninja/branches

Due to the nature of live video production, where unexpected changes to the app are not welcomed usually, I don't update https://vdo.ninja/ all that often. As well, constant updates to the primary hosted app makes supporting users challenging, as its hard to tell if an issue is with the code or with the user. For this reason, VDO.Ninja does infrequent updates to the primary hosted production version.  Users wanting newer features, or who have greater risk tolerance, should use alpha version at https://vdo.ninja/alpha/

## Server side / API software
Since VDO.Ninja uses peer-2-peer technology, video connections are made directly between viewer and publisher in 95% of cases. Hosting a TURN server yourself may help improve performance, but very few users will see an improvement to video quality by using one; most users will find using them harmful. They also will not help lower bandwidth usage or CPU usage, so generally you wish to avoid using them if possible.

Details on how to deploy a TURN server are provided; see: [turnserver.md](turnserver.md). For those capable of hosting their own TURN server, that would be appreciated if possible, as TURN servers are the largest cost incurred by VDO.Ninja at present. (other than time, of course)

Other than TURN servers, VDO.Ninja also uses public STUN servers and a hosted handshake server. These are used to facilitate the initial setup of peer connections and are generally not required after a peer connection is established. These servers are free to access and use, even for private deployments. You can host and customize your own handshake server as needed; please see details here: https://github.com/steveseguin/websocket_server

A design goal of VDO.Ninja is to be serverless and we are near 99% of the way there. This design objective ensures VDO.Ninja can be offered for free, along with providing increased levels of security and privacy.


https://vdo.ninja may unavoidably use cookies that are exempt from EU laws of requiring notice of their use; they are exempt as they are required and necessary for the technical functioning of the web service. Our webserver is cached by Cloudflare and it provides denial of server protection for the users of VDO.Ninja.

Additional security features are being added weekly on request. Please ask about these options if added security and privacy are requirements for you.


## Licence 
VDO.Ninja is available as 'mostly' open-source; please see the LICENCE.md file for details.

## Credit
Thank you to everyone who has helped support this project so far. From the moderators, volunteers helping with support, those contributing media assets, the project sponsors, those reporting issues, those offering feedback, and any code submissions.

## Contributors of this repo
<a href="https://github.com/detectivesheepy/vdosamurai/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=detectivesheepy/vdo.samurai" />
</a>
