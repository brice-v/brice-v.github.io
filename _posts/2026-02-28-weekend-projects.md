# Weekend Projects

This past weekend I decided to embark on 2 different but interesting projects. One was to make an update to a golang library that I wanted to try out, and the other was for a discord notifier that would work for my Minecraft Servers uptime.

## haproxy-discord-notifier

The name is straightforward because its very simple what this actually does but the implementation is a bit more interesting.

I host a Minecraft server for my friends (some more context [here](https://blog.bricev.xyz/2025/04/28/setting-up-a-minecraft-server.html)) but occasionally it goes down, for various reasons.

- Too much activity on the server causes it to restart
- Internet goes down (seems to be a regular enough occurence that maybe I should contact my ISP)
- Power goes out (this has also happened a surprising number of times)

These issues are not something that you would typically deal with if everything was just in the cloud _all_ the time. But I specifically run my server on a local machine because its just more economical to do so. Look up the cost of running a dedicated CPU with 12 Cores and 16GB+ of memory and you'll see what I mean.

However, this comes with the drawback that I dont get 9 nines of reliability (or whatever the cloud provider you use will give you). For something non-critical like a Minecraft server, this is perfectly reasonable. I take the server down regularly anyways for things like updates, backups, etc.

For this weekend side project, I essentially wanted a way to notify myself and my friends if the server went down for any reason. It avoids me needing to check the server manually and its more immediate feedback for the group as a whole. I knew this idea was feasible as I am already using [haproxy](https://github.com/haproxy/haproxy) and I noticied that it would broadcast out when it couldnt reach a backend. This most likely meant that there was some mechanism I could plug into to use.

Haproxy allows you to use email, which seemed like a perfect place to hook into. Email could work for me, but I didnt really feel like setting up proper emailing or using a third party service for something that essentially just needed to ping a group chat every so often. Based on [this blog post](https://mko.re/blog/haproxy-webhook-alerts/), I saw that someone else already had the same sort of idea and implemented it for slack. Mine just needed to work for Discord, which as long as they had WebHooks... ([yup](https://docs.discord.com/developers/resources/webhook#execute-webhook)), then I could adapt as needed.

The implementation part ended up being very straightforward, proxy connections for email to a fake server (the process that the notifier is running) and the post that off to the WebHook URL!

In a couple hours or less I had [haproxy-discord-notifier](https://github.com/brice-v/haproxy-discord-notifier), an extrememly simple program that I could run on my server and that would just post the full email text to a channel that I had created for the WebHook specifically. I added a bit more info for setup on that page in case anyone actually wanted to copy it and do their own thing with it but after testing it, everything worked and I was super happy that I didnt have to manually ping my group chat anymore when I had server issues!

## born

Recently, I have been getting interested in learning more ML and Deep Learning so I was curious if Go already had a library that was similar to torch or just had some basic capabilities that I could play around with and I found [born](https://github.com/born-ml/born). The project seems to be somewhat in early stages but already had _a lot_ of features and promise.

The key thing I just wanted to test was if the claims of 'no cgo gpu acceleration' would work for me as that would be really cool. Unfortunately, the library only seems to support that use case (currently) if you are on windows. Seeing as I only linux at the moment, I wasn't able to just build the default example that used GPU accelation. However! I was not deterred. This was a perfect excuse to dive in a bit and see what was going on.

There are quite a few libraries involved to make the 'no cgo' part work with regards to the GPU acceleration, however they are building on a WebGPU project that was esstablished in the Rust community [wgpu_native](https://github.com/gfx-rs/wgpu-native), which to me meant that there most likely was another library in Go that already used CGO to interact with this library and sure enough I found [this](github.com/cogentcore/webgpu). This meant that all I really needed to do to test this out was fork the library and plug in all the pieces of the 'no cgo' version with this library to hopefully get it to work on linux.

In a couple hours or less I had [my fork](https://github.com/brice-v/born), and with it I was able to run the gpu accelerated example with everything working! (some debugging necessary in the middle there but when isnt there) This meant at the very least I could try out some of the libraries feature while still getting to benefit from gpu acceleration, at least until the library implements it. Or if I get around to trying to make this a proper merge. However, I would only want to do that if I could stick to the projects initial goal of 'no cgo'. I do still think that a go library in an ideal world should try to let you build with cgo enabled or disabled but based on what I was seeing it might not be possible with the current ffi strategy that's used.

Anyways, it was another successful weekend project.

## Thoughts

I think weekend projects are always fun, but the thing thats strict about them is you have to be able to actually get something done within the timeframe of the weekend. I only had a day really to try and accomplish something and these 2 things were just on the top of my mind at the time. My real project I've been working on for quite a while is my programming language but that is much more involved and I've also been working on it here and there for the past 6 years, so something small to take a break from that is always good.

Weekend projects, dont need to be perfect or even presentable, but I think when you have a problem and you know it can be solved, sometimes waiting till the weekend is best so you can actually get some real work done. This weekend I dont know what I have planned, but I know I wanted to write this blog post. Hopefully it can encourage others to just write something that suits their needs and is fun!
