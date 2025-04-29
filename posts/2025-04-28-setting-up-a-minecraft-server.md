# Setting up a Minecraft Server in 2025 was Surprisingly Easy

## Some History

I feel like every year there's a time when I decide I want to hop in and play Minecraft again. Its one of those games that you can just spend some time messing around in for a couple hours (to a couple months) and then be done with it to come back another time.

Many times I play, I'd rather just play online with friends but it's not always just a 1-click solution for people in the way that many games are. Of course I'm primarily referring to PC. On Console, I assume this is usually a super simple process but it has been quite a while since I've played on console. The last time being my Xbox 360 around the time it came out (2012!)

It's awesome to see nowadays that Minecraft is still alive and well, with many fans and kids growing up with it.

Although I mention playing it on console (and this is a bit of a tangent). I originally started playing it back in Beta around the time of the Nether update. Part of the reason I still come back to it, is just the fact that it holds a nostalgic place in my heart and it is still updated on a regular cadence.

## Back to the regularly scheduled technical parts

In year's past, the way I used to run a server was simple. I used a program called Hamachi which essentially allowed a virtual private network between some user's PCs and that would allow everyone to connect to the server. It worked, it was simple, and it was free (enough). I think the free version only allows up to 5 people and when you don't have a lot of resources to dedicate to a server, or money for hosting, or enough friends to exceed that cap, then it was exactly what I needed, when I needed it.

I haven't done too much research into free hosting that's way more common today than it was back in ~2010. Or the myriad of other ways that are accessible to setup a server, including Bedrock edition but that is mainly due to the fact that I had some know-how now that I didn't have back then. And also, because this is important to mention, some disposable income to spend on a small server on a cloud hosting site.

_Okay I lied, the above part wasn't that technical, but I needed more context to give to my current solution_

## My Self Hosting Setup

Requirements 

- Tailscale
- Server (on a cloud hosting site)
- Server (available to you, _this will actually run Minecraft Server_)

That was all I needed, I tried this once before and couldn't figure out the reason I was having trouble (so I ended up doing something else entirely).
After coming back to it over a year later, I realized it was much simpler than I thought.

### What do those do?

Tailscale is used to connect from my Server on a cloud hosting provider to my local server running on my local network (i.e. where Minecraft server is running)

The server on the cloud hosting provider is really just used for its public IP address, but it allows me to forward traffic from the standard Minecraft server port (25565) to the port in my Tailscale network that is running the Minecraft server.

The server at home, well that just runs the Minecraft server. Pick any provider you like and set it up the way you like and put your Tailscale IP address as the Minecraft server address.

### Additional Things

Setting up a firewall, whitelist, and automatic security updates are all probably things you should do too. Authentication plugins for your server are also a decent idea. At the end of the day, if Minecraft is just for you and your friends, its okay for down time and maintenance and even world transfers to other servers. Keep it simple, keep it secure.

### My Initial Mistake

When setting this up over a year ago, it turns out I was accidentally trying to forward HTTP traffic, which is a simple mistake but at the time I was just trying to play so I didn't look too much into it. Coming back to it, I realized my mistake and was very easily able to update it properly to forward the Minecraft client's tcp traffic.

## Closing thoughts

I realize this is not an actual guide and it isn't supposed to be. If you have enough technical know-how, all of this is within grasp to you already. I was just happy to be able to play Minecraft with some friends again. We'll see how long the server lasts this year lol.