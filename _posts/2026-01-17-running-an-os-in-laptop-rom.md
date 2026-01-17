WIP

# Running an OS in the BIOS

Recently I saw a video about flashing [coreboot](https://www.coreboot.org/) onto a Thinkpad without requiring any custom rom flasher.
This interested me because I was always interested in running coreboot on my laptop and I hadn't gotten around to buying a custom flasher or attempting it myself.

## Setup

In order to get this to work, their was 2 pieces of software that I would need to use and maybe a bit of hope that I didn't brick anything.

1. [1vyrain](https://github.com/n4ru/1vyrain)
2. [skulls](https://github.com/merge/skulls)

1vyrain is itself a sort of custom bios which offers some options not offered by the default bios of a certain age of Thinkpad.
There are some benefits to using it but I was mainly interested in its ability to load custom payloads which would allow me to load coreboot.

skulls on the other hand is essentially a pre-built coreboot payload but there are some niceities in the repo that made it easier to do what I was trying to do.

## Running

By following all the steps in the 1vyrain readme, you will eventually get to a step where it mentions [custom binaries](https://github.com/n4ru/1vyrain?tab=readme-ov-file#custom-binaries). At this point, I loaded my skulls image (specifically the "top" rom) by having it on another computer running `python -m http.server`. By doing that I could easily `wget` the image without having any secure connection.
I then verified the 



- mention kolibrios
- Include exact steps I ran to actually build and then create the image with kolibrios
- redo this myself
- take a screenshot or video into gif
- mention steps to revert (include GRUB_CMDLINE_DEFAULT options)