<h1 align="center">
    <a href="https://expose.sh/#gh-light-mode-only">
    <img src="https://raw.githubusercontent.com/exposesh/.github/main/assets/expose_logo_black.svg">
    </a>
    <a href="https://expose.sh/#gh-dark-mode-only">
    <img src="https://raw.githubusercontent.com/exposesh/.github/main/assets/expose_logo_white.svg">
    </a>
</h1>
<p align="center">
    <a href="#about">About</a> •
    <a href="#demo">Demo</a> •
    <a href="#features">Features</a> •
    <a href="#use-cases">Use-cases</a> •
    <a href="#access">Access</a> •
    <a href="#free-and-premium">Free and Premium</a> •
    <a href="#learn-more">Learn more</a>
    <a href="#faqs">FAQs</a>
</p>

# About

EXPOSE is your new favourite open source tool for exposing your local services on the public Internet.  
With no installation or configuration required, you can use it.  
In fact, EXPOSE relies on your SSH client.   
Authentication is done using the public SSH keys you have on your GitHub account. If you don't have any, you can [read this article](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account).  
So all you have to do to expose, for exemple, `localhost:3000`, is type `ssh -R 1:localhost:3000 expose.sh` in your terminal.  
If you use a different username on your computer than the one you use on GitHub, add the GitHub username to your SSH command (example: `ssh -R 1:localhost:3000 yourusername@expose.sh`).

# Demo

https://github.com/exposesh/.github/assets/81755261/b777c15d-6024-42a9-8aa9-1554179ffc14

# Features

- Nothing to install: use only your terminal and SSH client
- Nothing to configure: automatically retrieve public SSH keys from your GitHub account to authenticate yourself
- Custom URL based on your GitHub username
- HTTP & HTTPS & WebSocket supported
- Displays a QR code for easy testing on a mobile device
- Several services can be exposed at the same time
- Distributed system designed for speed
- Global routing for the fastest possible access to your services on the other side of the world
- Secure
- Open source

# Use-cases

- Demos and presentations: streamlines the presentation of your applications or services by providing the capability to access them seamlessly from any device with internet connectivity
- Mobile development: run the back-end for your Android or iOS app locally and make it accessible to your app
- Webhook testing: highly beneficial for the testing and troubleshooting of webhooks, as it facilitates the exposure of a local endpoint. This makes it simple to test webhook requests from external services such as payment gateways, messaging platforms or API
- Expose your home server: make your local server, like your Raspberry Pi, easily accessible on the public Internet
- Easily test your app: ensure your application looks and functions flawlessly on devices of all shapes and sizes
- And many more...

# Access

To prevent malicious use of EXPOSE, you should add a star to one of the project repositories.  
Of course, if you wish, you can add stars to all the repositories. 😄

# Free and Premium

Infrastructure is expensive, but at the same time everyone should have access to a high-performance tool of this kind.  
The free version of EXPOSE is limited to two local service exposures at a time, with a bandwidth of 100 kb/s and a maximum duration of 15 minutes per use.  
Of course, you can reconnect as often as you like.

By supporting this independent, open-source project through GitHub Sponsors and a monthly subscription of $5, you unlock all the features.  

# Learn more

Find out more about how EXPOSE works by visiting the following repositories:

- [expose-server](https://github.com/exposesh/expose-server): the heart of EXPOSE with the SSH server and the Web server, all on a distributed infrastructure thanks to [Fly.io](https://fly.io)
- [expose-functions](https://github.com/exposesh/expose-functions): Firebase Functions for managing GitHub webhooks, verifying users and retrieving SSH public keys
- [expose-banners](https://github.com/exposesh/expose-banners): the various texts displayed when connecting to the SSH server

# FAQs

<details>
<summary>Is EXPOSE secure?</summary>
<strong>Yes</strong>, SSH is an encrypted protocol, and access to your application is secure thanks to the automatic certificate attached to the HTTPS endpoint.
</details>

<details>
<summary>What do you mean by no installation and no configuration?</summary>
<strong>No installation</strong>, because EXPOSE uses the SSH client present on your device, available by default on all current operating systems.<br><strong>No configuration</strong>, because EXPOSE automatically retrieves the data provided by your SSH client and GitHub account.
</details>

<details>
<summary>What are the limitations of the free EXPOSE version?</summary>
The free version of EXPOSE is limited to two local service tunnels at a time, with a bandwidth of 100 kB/s and a maximum duration of 15 minutes per use.  
</details>

<details>
<summary>How can I access the unlimited version of EXPOSE?</summary>
By supporting this independent, open-source project through <strong>GitHub Sponsors</strong> and a monthly subscription of $5, you unlock all the features. 
</details>

<details>
<summary>Is it possible to generate several tunnels at once?</summary>
<strong>Yes</strong>, you can create several tunnels at once by repeating `-R `. For example: <code>ssh -R 1:localhost:port1 -R 2:localhost:port2 expose.sh</code> 
</details>

<details>
<summary>I bought a subscription but when I connect to EXPOSE, it is still the free version?</summary>
Do not panic! Check if your computer's current username matches the username of your GitHub account. If it does not, add it to your SSH command. For example: <code>ssh -R 1:localhost:port yourgithubusername@expose.sh</code>
</details>

<details>
<summary>The username matches well, but I am still on the free version of EXPOSE...</summary>
Do you have a private SSH key on your device that corresponds to a public SSH key on your GitHub account? You can find your GitHub's public SSH keys by clicking on your profile picture, then on Settings, then in the "Access" section, click on "SSH and GPG keys". Perhaps you have too many SSH keys on your device and your SSH client is getting tangled up? In that case, specify in your command where your private SSH key is located: <code>ssh -o IdentitiesOnly=yes -i /path/to/private/key -R 1:localhost:port yourgithubusername@expose.sh</code>
</details>

<details>
<summary>I see "Cannot connect to your local application. Please check your terminal for hints." in the browser!</summary>
Review the currently running SSH command for any clues, and ensure that your local application is reachable on localhost with the specified port. You can verify this accessibility by navigating to <code>http://localhost:port</code> in your browser.
</details>

<details>
<summary>I see "connect_to localhost port *: failed" in the terminal!</summary>
Ensure that your local application is reachable on localhost with the specified port by navigating to <code>http://localhost:port</code> in your browser.
</details>

<details>
<summary>How is it possible to have my SSH client automatically reconnect to EXPOSE?</summary>
It is true that disconnections are not fun... You can modify your SSH command in this way to reconnect automatically: <code>until ssh -R 1:localhost:port expose.sh; do echo Reconnecting...; done</code><br>Ah, ha, ha, ha, stayin' alive, stayin' alive 🎵😌✊
</details>

<details>
<summary>Does EXPOSE support other protocols?</summary>
EXPOSE supports other Web protocols such as WebSocket. An EXPOSE extension, which can be installed on your devices, is planned to facilitate the use of TCP and UDP protocols by EXPOSE tunnels.
</details>

<details>
<summary>Where do I contact someone if I have a question or an issue?</summary>
You can open an issue on the <a href="https://github.com/exposesh/expose-server">server repository</a> or send an email at <a href="mailto:gaetan@expose.sh">gaetan@expose.sh</a>.
</details>
