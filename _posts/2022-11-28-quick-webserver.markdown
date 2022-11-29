---
layout: post
title:  "Simple Zero-Config Web Server"
date:   2022-11-28 12:00:00 -0500
categories: nodejs npm brew http
---

Recently while working on an internet-of-things project I had a need for a very simple web server to serve a binary file for testingthe  over-the-air updates mechanism of the ESP32 microcontroller. While the final solution was likely to be different, I just needed something I could stand up very quickly on my dev machine and confirm functonality of the microcontroller code.

I didn't want to have to spend time searching for whatever was the new, preferred hotness when it came to web servers, nor did I want to sift through the simpliest way to configure one once I settled. I really just want a stupid simple server that I could run with a single command line, view activity info within the terminal and where the configurations were only the bare minimum.

After some searching I managed to stumble across a package called `http-server` from NPM.

![http-server](/assets/images/http-server.png)

Given my dev machine is currently a Mac and I'm a [Homebrew user][homebrew-mac], installing `http-server` was extremely quick:

~~~
brew install http-server
~~~

This installed `http-server` for global use on my machine. Now to run the server it was as simple as running the following command:

~~~
http-server
~~~

The server immediately started running and would by default server `./public/` if the folder exists or `./` otherwise.

Navigated to my browser at `http://127.0.0.1:8080` to confirm it was running and then I was golden!
This was a very quick and convenient way to serve files over HTTP with little to no configuration in as little as minutes.

![http-server-window](/assets/images/http-server-window.png)

If by chance you do need more configuration options, check out the links below for more details. There are ways to configure username & password authentication and even HTTP over TLS (HTTPS).

**NPM:** [https://www.npmjs.com/package/http-server][http-server-npm]

**Github:** [https://github.com/http-party/http-server][http-server-gh]

[homebrew-mac]: https://brew.sh/
[http-server-npm]: https://www.npmjs.com/package/http-server
[http-server-gh]: https://github.com/http-party/http-server