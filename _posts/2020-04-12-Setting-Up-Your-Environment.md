---
title: "Setting up your Environment"
categories:
  - Capture The Flag/Pentesting
---

# Programs you will need

* A linux, mac or Windows machine 
* Virtualization software (VMware, Virtualbox)
* Kali Linux, Parrot Security or your favorite security linux distro

I have all 3 operating systems on different machines, but I'll be using my linux machine for these articles. I will also be using Virtualbox and Kali Linux for my virtual set up. It is alright if you use other programs, but all screenshots will be of Kali Linux and Virtualbox. 

### Setting up Virtualbox

First thing you'll need to do is set up your virtualized environment.

What is virtualization? Essentially, this is way to emulate other operating systems on your computer without having to buy specific hardware tied to that operating system. Long gone are the days where you'd have to buy another computer with an operating system pre-installed in order to see how it works. Now you can use your existing computer's resources and create a virtualized environment of pretty much any opertating system you can think of. 

If you go to the [Virtual Box downloads page](https://www.virtualbox.org/wiki/Downloads), you will be presented with this page:

![virtual box downloads]({{ site.url }}{{ site.baseurl }}/assets/images/virtualboxdownload.png){: .full}

Download the appropriate version for your computer and follow the instructions to complete the installation. You may also be prompted to download the extensions pack, which you should do. Once everything is installed, you should be looking at a GUI like this:

![virtual box main]({{ site.url }}{{ site.baseurl }}/assets/images/virtualboxmain.png){: .full}

As you can see I already have kali and parrot set up, as well as a practice vm. 

### Setting up Kali Linux

Now we'll need to downlaod our security pentesting platform. 

What is Kali Linux? Kali Linux is an all purpose pentesting linux distribution created by Offensive Security. It comes pre-packaged with hundreds of tools that pentesters use in real life engagements. This makes this distro very powerful and it can definitely be used maliciously or stupidly, depending on the user. If you want to get your feet wet with linux, I reccommend starting with a distro like Ubuntu. You will need to know basic linux commands to be able to properly set up/maintain the distribution, as well as use the various tools. 

You have a couple of different ways to install Kali linux, but the easiest way is to download the virtual box file and import it into your virtual box program. You can get to the downloads page for virtual box [here](https://www.offensive-security.com/kali-linux-vm-vmware-virtualbox-image-download/). I downloaded the 64 bit program because I'm running 64 bit on my operating system, which most up to date systems should be running. 

Once you've downloaded Kali, open up virtual box and click on File -> Import Appliance. Click on the file icon and find where you downloaded the kali image. You will end up at a screen like this:

![import kali]({{ site.url }}{{ site.baseurl }}/assets/images/kaliimport.png){: .full}

Leave all of the default options on and click "import." 

After finishing, you should be able to see your imported machine. Run the machine to make sure it turns on and you can get to the home page. By default, the username and password is kali/kali. This is different than previous versions where the username and password were root/toor. You no longer have root privileges on the newest versions of Kali. 




