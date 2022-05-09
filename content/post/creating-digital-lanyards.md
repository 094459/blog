---

title: 'Experimenting with digital lanyards - introducing the Badger2040'
date: '2022-05-09'
tags : [ Internet of Things, aws open source, Pimoroni, Badger2040]

---

## Experimenting with digital lanyards

As someone who attends events on a regular basis, I have spent a fair bit of time over the years looking at interesting ways to engage with attendees. One of the problems I was looking to solve was how do I share useful information with attendees without having to interrupt the conversations (something that typically happens as I try and find those links on my mobile phone). 

I am always looking at interesting new devices that might help, and recently I was drawn to an announcement from Pimoroni about a device called the [Badger2040](https://aws-oss.beachgeek.co.uk/1o1), a low cost e-Ink display that was combined with a [Raspberry Pi Pico controller](https://aws-oss.beachgeek.co.uk/1o2).

> *If you work or even dabble in the Raspberry Pi/ Maker space, you will know who this is, if not then head over to their site and prepare to be inspired and excited in equal measure*

The device has a number of buttons that you can use to make it more dynamic - for example, you can switch information you want to display or enable some basic interactivity potentially. Cool stuff I think, with lots of potential. 

I actually bought one of these a few weeks ago, and put together over a couple of hours, a very simple sample application that is perfect for my use case. I shared it on social media today, and this [tweet](https://twitter.com/094459/status/1523574076199305217) generated a fair bit of interest. I had a few questions so thought I would quickly put together this post to share what it is and how to get it up and running in case anyone else wants to try them out.

**Introducing the Badger2040**

As this post, [Getting Started with Badger 2040](https://aws-oss.beachgeek.co.uk/1o1) on the Pimoroni site says, the Badger2040 is a:

> "a low cost, RP2040-powered eInk/ePaper/EPD programmable badge"
> 

To get started with this, you are going to need the following:

* a Badger2040 kit - this comes with a battery pack, velcro, a lanyard and a USB-C/USB connection cable
* [Thonny](https://aws-oss.beachgeek.co.uk/1o4) - an open source Python IDE that allows you to connect and upload/download code and assets to the Badger2040. This works on Mac, Windows and Linux.
* access to the [GitHub repository that contains useful example code](https://aws-oss.beachgeek.co.uk/1o3)

**Installing Thonny**

I had never heard of [Thonny](https://aws-oss.beachgeek.co.uk/1o4) before, but it is a very simple code editor that is optimised for this kind of use case. When you add files, it asks you whether you want to work on that file locally, or directly on the remote (i.e. Badger2040) device. Thonny is the way to effectively deploy your code to the device.

It was simple enough to install on my Mac, and just installed using the defaults. To get ready for development, you need to first configure the runtime. To do this, from the TOOLS > OPTIONS, select the INTERRUPTER tab and from the pull down, select MICROPYTHON (RASPBERRY PI PICO).

![screen shot of thonny configuring the interpreter](https://github.com/094459/badger2040/blob/main/images/thonny-1.png?raw=true)

Below this, you should see PORTS - you can leave that alone as it should automatically configure. See the next step as to how this might be helpful when troubleshooting issues.

**Connecting to the Badger2040**

I am using a Macbook running Big Sur, and in a hurry to get up and running (and of course, ignoring the documentation) I connected the battery pack to the Badger2040, connected the USBC cable to my Mac and then booted up Thonny. 

I encountered an error however.

```
Device is busy or does not respond.
```

I checked to see if I had configured everything correctly by checking the TOOLS > OPTIONS and viewing the PORTS section under the INTERRUPTER tab. You should see a value that says something like "BOARD IN FS MODE (/dev/cu.usbmodem14201)". This appeared so I was not sure why I could not connect.

I quickly figured out my problem. I had connected the battery pack, and I had switched it ON. This meant that the Badger2040 was actually running and so I could not connect to it (as it was busy). Once I turned the battery pack OFF, and then retried, I could successfully connect to the Badger2040, and I could see both my local files as well as the files on the Badger2040. I hope that saves folk some time!

> **Updating the Firmware**
> I will not cover it in this post, as it is covered very well in the Pimoroni post linked above. You are able to upload firmware to the Badger2040 by simply putting the device in boot rom mode (this makes the device appear as a drive in Finder) and then copying the uf2 file into the folder. Once copied, the update happens automatically. You probably will not need to do this if you are just getting everything up and running, but if you do, check out the post above.
> 

**Working with images**

It is possible to display low resolution images on your badger2040, and I actually really like the lowfi, retro feel of them. So I can hear you all asking me, how?

Pimoroni provide lots of useful tools, and an image conversion is one such useful tool. You can find it [here](https://github.com/pimoroni/pimoroni-pico/tree/main/examples/badger2040), and the way that I created my image file (it is in the GitHub repo which I share at the end of this post) I did the following:

* clone the repository, so I could use the convert.py script
* resize an image I wanted to use so that it was exactly 104 pixels in width and 128 pixels in height
* run the convert.py script using the command:
* ``` python3 convert.py --binary images/ricsue.png ``` 
* this creates an output file in the same folder, called ricsue.bin, which is the binary image format that the badger can use

There are more examples of how you can work with images in the Pimoroni blog post, so check them out.

**My customised badger2040**

The Badger2040 comes a ton a sample applications, two of which I realised I wanted to mesh - the qrcode and the badge scripts. One allows you to configure QR codes to be displayed, with some text, using a text file to configure the URL and generate the QR code. The other allows you to display a static image with some text. I wanted to use both, and then use the buttons on the device to toggle which one, depending on where I was or what I was doing at a given time at the event.

I am not going to cover the code, as it is heavily based on the sample code. You can find the code I used for my badge over [at this GitHub repo](https://github.com/094459/badger2040). It is not the best code in the world, but I hacked it together using the sample applications so I would recommend going through those to see what you can use.

I hope that you find this interesting, and will post back my findings of using this device at events over the coming weeks as I have quite a few coming up.