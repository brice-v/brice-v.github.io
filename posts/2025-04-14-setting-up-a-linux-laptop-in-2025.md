# Setting up a Linux Laptop in 2025

## The History

I've been running linux on laptops for about 10 years at this point. It first started when I had a sort of netbook in college and it just barely run the windows 8 that was on it. Linux was still new to me at the time but I had heard things about it bringing life to old computers so I figured it was worth a shot.

One Ubuntu install later and I had a "fast" system, at least when comparing it to windows, and many other random things broken (trackpad, wifi). This wasn't a great first impression but with some effort I managed to get those working, and in the end I installed a "user" friendly Arch derivative. Which believe it or not was enough to make things work. I would guess it was likely due to a newer kernel or some other reason but things worked. I kept that installed for a while until I finally had enough money to get a new laptop, and this time I decided on a Thinkpad.

My thinkpad was a freeing experience when it came to compatibility. No more broken wifi, no more broken touchpad (and even if it did, I had the trackpoint). It was awesome to be able to try out so many more Distros and I hopped from one to the next wiping my system along the way. Although I likely tried to keep a windows install around (at least my files) because of school at the time. The upgradeability was also huge and I was able to update the ram and storage as I needed and then to an SSD when I couldnt stand waiting on hard drive speeds any longer.

After college, I stuck with the same x230 thinkpad, and bought a new one when the old one died some mysterious death due to power issues (I bought a shell with the same or better processor and swapped all my old parts into it). At this point, I was kind of tired of wiping my drive and losing data accidentally so I installed Mint and that was pretty much the end of it. Mint is great, works well and I still have it installed as a dual boot on my desktop.

Somewhat recently (read: 2 years ago) I bought a new laptop that is the culprit of this blog post. I wanted something more modern, RAM, CPU, Screen, Batter Life - the works.  At first I considered a Mac, because the battery life is just superb, but the cost is still out of my reasonable price range.  I considered a framework, and still do to this day just because I heavily support what they've so far built and accomplished but again, cost seemed to be out of my reasonable range.  I ended up going to Microcenter and found a used Lenovo IdeaPad Flex 5 14" laptop for a reasonable price. The specs were good! Ryzen 7 (8c,16t), 2240x1400 16:10 display, 16GB RAM, and 256GB of storage. The battery life was still to be determined, and the storage was not as much as my x230 whic I had put 512GB in, but it was NVME so I excused it - and it was upgradeable.

## The Setup

The IdeaPad was running Windows 11 since I bought it 2 years ago. Honestly, I had wanted to use linux but on the first day of attempting Ubuntu on a Live USB I ran into some issues and I just wanted my laptop to work so I decided I would stick with it and just see how bad Windows 11 could really be.

After using it for the past 2 years, I think generally it was fine. Windows 11 performance leaves a lot to be desired however. Everything has a slugishness to it that I cant quite explain. I think the file explorer alone made me want to switch off. Nothing about it is quick, windows search is awful, the antivirus constantly runs and makes building software more painful. Theres some nice features though and it does mostly "just work" but Linux is still my OS of choice and I was ready to give it a proper shot.

## Choice Paralysis

When deciding on a Linux Distro there are many _many_ choices. I've used a fair amount of popular ones and tried out other smaller ones, but I wanted mostly a system that would "just work" and ideally work for all the hardware I had on this laptop. The biggest glaring thing to me was touch screen and that I really needed Fractional Scaling. We've come a long way since 2014 so I was optimisitc

The choices I went through were as follows:
* [Ubuntu](https://ubuntu.com/) (24.04)
* [Manjaro](https://manjaro.org/) (Latest)
* [Pop!\_OS](https://system76.com/pop/) (22.04)
* [Kubuntu](https://kubuntu.org/) (24.04)
* [Mint](https://www.linuxmint.com/) (22.1)
* [elementary OS](https://elementary.io/) (8.0.1)
* [Zorin OS](https://zorin.com/os/)  (17.3)
* [Cachy OS](https://cachyos.org/) (Latest)

I mostly stuck with LTS releases and in general something Deriving from Debian/Ubuntu so I could stick with apt which I am most familiary with at this point. I stuck Manjaro in there because I've had luck in the past with it working on newer hardware and in general it was easy enough to use. CachyOS was just something I saw on Distrowatch so I decided to try it out as well.

## The Initial Impressions

Using a Live USB here are my initial impressions of all the above and if I thought they may be able to work for me

* Ubuntu
	* Huge installer for some reason
	* Snaps for a lot of packages - still down love the non-native package method
	* Touchscreen keyboard did not work at all in live USB
		* later on I did install it fully and that seemed to work but I had already made up my mind on another Disto
	* Experimental support for ZFS! Very cool (lets see if that works later on)
	* Weird issue with fractional scaling causing black rectangles behind some windows
* Manjaro
	* Failed out of the gate to get it to boot to Live USB
		* Tried with and without Secure boot but no luck
		* Verified the checksum and everything but no dice there either
			* I was using ventoy but this was the only distro with the issue so maybe it wasnt meant to be
* Pop!\_OS
	* Another failure to boot ot Live USB
		* I had other Ubuntu distos to try out so I wasn't too bummed
* Kubutu
	* First time trying it
	* actually worked out of the box
	* touchscreen seemed usable
	* Left this as a solid consideration
* Mint
	* Very familiar with Mint but the touch screen behavior just wasnt good enough for what I wanted
	* It was going to be my #2 though after
* elementary OS
	* Random issues that I can't quite remember but the major turn off is no guarantees for clean upgrade path
	* I used to use elementary a bunch but I remember wanting to upgrade and having no easy path forward so I've stuck to other distros
* Zorin OS
	* Pretty nice behavior
	* Everything worked
		* Touchscreen behavior was exactly as I hoped
	* Hey Look they also have ZFS support (although it doesnt say experimental strangely, Ill still consider it so)
	* This looks to be a solid contender and I've never used it before (but heard lots about it over the years)
* Cachy OS
	* This worked out of the box
	* Supposedly faster but I'm not sure I would really notice considering I was coming off using Windows 11 for a while
	* Mostly wanted to try it out to test the speed
	* Worked for what I needed

## The Choice

I decided on Zorin as I liked the way it worked, I've never tried it before, they had an upgrade feature for major version increments ([here](https://help.zorin.com/docs/getting-started/upgrade-zorin-os/)), and I would be able to try out ZFS on Root.

## The ACTUAL Setup

I'm used to setting up my laptop in a very particular way and the requirement of some hoops that may need to be jumped through to get everything working the way I like. Initial setup of everything was actually quite easy. Install, reboot, update, etc.

### A Problem Occurs

Shutting the screen on my laptop should mean don't use any power until I wake you back up. That is not really the case nowadays and I've heard plenty of horror stories as well as experiencing my own. I don't want my laptop to be 100 degrees if I pull it out of my backpack. I dont need updates happening because my screen is closed. If I shut the lid tonight, tomorrow when I wake up I should be able to open my laptop and see it at the same % it was at the day before. This is not the case. It wasn't the case for me on windows and so I decided to just hibernate on lid close.

I would think that hibernate is fairly straighforward but that was my mistake. It turns out this is not really natively supported, at least not on Zorin or Ubunutu and possibly many other distros but I _need_ this feature to work. A laptop that loses +/-30% overnight is not worth it to me. In my mind, if I'm not using it, it should be just how I left it.

There was countless troubleshooting steps I went through, blog posts, forum posts, all to see if I can just get this up and running easily.

Here were my mistakes:

* Using ZFS
	* Apparently not well supported (yea this is my bad lol but I wanted to try ZFS out)
	* _maybe_ possible with a swap partition
	* Later reading, led me to realize this but I went through all the steps and got to a point where I could Hibernate, but resume would act as reboot
		* This _may_ have been a fine alternative but I really wanted my laptop to pickup from where I left off
* Having Secure Boot on
	* I probably honestly just missed a line in a post somewhere to turn this off but it took me way to long to realize I needed this off
* Using Encryption
	* At first I had ZFS fully encrypted, and got to the point I mentioned above but decided against it
	* I eventually, once I realized my mistakes got FDE (full disk encryption) setup properly and can resume exactly as I wanted

How I resolved it:

Eventually, I read a zorin forum post, that led me to an askubuntu page which was precisely what I was trying to accomplish. FDE setup with an encypted root install. For reference: [the steps I followed](https://askubuntu.com/questions/1441208/encrypted-partitions-luks-with-login-password-hibernate). Sadly I can't find that original Zorin forum thread that led me there but shoutout to that person who helped me on my way. The askubuntu thread above was exactly enough information for me (in addition to my prior attempts) that allowed me to get everything setup just as I hoped.

#### Another Problem Occurs

After I had hibernate and FDE, I was pretty much all set. I started downloading packages, signing in to accounts, ssh keys, etc. None of that was broken but then I tried to use [VSCodium](https://vscodium.com/) and the text just looked blurry. My guess was this was related to the fractional scaling and sure enough, when setting it back to 100% this was the issue. Turns out this was due to wayland. It's been so long of wayland being ready/not-ready so when I saw this I was just like "wow, I can't believe I'm on wayland". But that's great! I'm glad for the forward progress and not even noticing a change such as my display server is a great sign. The issue ending up being pretty simple to solve with just some arguments passed to the program.

## Summary

I doubt I'm out of the woods yet, but I'm super optimistic about the linux laptop desktop as a whole. It's fast, customizable, and when everything is working nicely, it gets out of my way to let me get some work done!

(Side note but I ironically have hit another wayland text issue since this with IntelliJ and a steam crash/hang that I just solved by installing from flatpak lol)

I really think if you are hestiating using linux on your laptop, you should'nt. With Windows 10 going [EOL](https://support.microsoft.com/en-us/windows/windows-10-supports-ends-on-october-14-2025-2ca8b313-1946-43d3-b55c-2b95b107f281) this year, I know I'll be attempting an upgrade of my desktop to be full on linux but thats a story for another time.


Thanks for reading! (This is my first real blog post so if it rambles its mostly from stream of conciousness. I'll get things better setup in the future but felt like the first step of writing for a blog is just getting something out there. Feel free to send a PR on my [GH](https://github.com/brice-v/brice-v.github.io) if you notice any typos and I'll correct them and re-push)
