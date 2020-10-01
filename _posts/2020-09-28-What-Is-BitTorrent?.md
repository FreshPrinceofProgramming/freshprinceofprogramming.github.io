---
title: "What is BitTorrent?"
categories:
  - What The Hack
header:
  image: assets/images/nickyoung.jpg
  
---

Torrenting, although somewhat of an old concept, is still very much relevant today. Often it is brought up in terms of illegal activity where you might torrent a new movie, video game or piece of softwware. While this can be true, the workings behind torrenting and how it functions are largely left unnocticed to the end user. In this article, I'll attempt to explain what torrenting is and how it affects cyber security.

### The Shortest Distance Between Two Points Is...

Let's talk about the most common way devices connect over the internet: the **client-server model**. This may sound very familiar if you read my [VPN](https://freshprinceofhacking.github.io/what%20the%20hack/What-Is-A-VPN/) article. To recap, essentially the way that we are used to seeing our devices connect to websites on the internet is through this method. The client machine(our device) connects to a server, which hosts the content we want to see. Very simple. 

![Csmodel]({{ site.url }}{{ site.baseurl }}/assets/images/csmodel.jpg)

This means that when we are also downloading content, we follow this same model. But let's think about this for a bit. Imagine if we wanted to download a file from a popular website. We would need to A) connect to the website and then B) request the download from the server it's hosted on. This works normally, except that this particular day the website is experiencing some slow down due to the high volume of traffic going to it. We're still able to request a download for the file, but it's taking forever. What could be happening is that the server is experiencing overload, and it is bottlenecking your request for the download, which causes the slow speed. Even though we have a direct download from the website itself, this looks to be the slowest way possible to get the file. I'm sure we've all been in this situation. It would help if there was an alternative way to download the file...

### Be Kind To Your Peers

It turns out we're in luck! We notice that the site is also hosting a torrent of the file. All we have to do is download the torrent, fire up our old torrenting software, and BAM we have the 20gb file in only 30 minutes.

"Wait! What happened!? Why was it so fast??" 

I'm glad you asked! The answer is trusting your peers to help.

I guess that doesn't make a lot of sense from the surface, but bear with me for a bit. Let's imagine a different way to share/download data over the internet. We have the client-server model, although sufficient in most cases, in certain circumstances isn't the most ideal. What if there was a way to share a download with multiple clients so that instead of relying on the website itself to serve the download to us, we can directly get the file from EVERYONE that has it? That might be a faster alternative, but how would we do that?

This is where things get interesting. We are now going to switch from the client-server model to the **Peer-to-Peer**(P2P) model for file sharing and downloads. As the name suggests, we are going to be relying on our "peers"(client devices) to be able to handle the task of sharing the files we want to download. This means that every client also now acts a server. We've decentralized the connection that has to be made to a hosting server for content, and burdened the connections on every peer within our network. So now that 20gb file that was taking 4 hours to download from a main server is being shared amongst peers, and each peer is taking pieces of the file from each other to complete the download. Here's what a P2P network may look like:

![P2P]({{ site.url }}{{ site.baseurl }}/assets/images/p2p.jpg)

As we can see, each peer is connected to each other for sharing the resource they need to download. P2P networks come in many different forms and can enhance tasks in a variety of ways. One of the most famous P2P type networks is the **SETI** (Search for Extraterrestrial Intelligence) project. Operated by researchers out of UC Berkeley, this network uses idle computers to contribute their resources for using radio telescopes to listen for signals coming from space. Anyone can contribute to this project! I recommend checking the [website](https://seti.berkeley.edu/) out for more information. It's a lot more complicated than just setting up a normal P2P network, but conceptually this is the driving force behind it. 

### I'm Just Following Protocol

So we can find potential alien life using P2P networks. That's cool! But that doesn't help us understand how Bittorrent works. Now that we have a better overall understanding of how P2P networks work, we can start to talk about Bittorrent.

Bittorent is just a **protocol** that uses P2P to operate. I briefly touched on what protocols were in [one of my articles](https://freshprinceofhacking.github.io/capture%20the%20flag/pentesting/Ports-&-Protocols/). Essentially, a protocol (in a computer sense) is method or way of communication. There are tons of protocols out there that devices use to communicater with each other and perform tasks. Bittorent is one of these protocols. So how does Bittorent actually work? First we'll need to explain some key concepts of Bittorrent:

* **Seed**: This is the originating server that holds the original file to download and splits the file up into many pieces
* **Tracker**: The tracker is part of a .torrent file that contains information on where the pieces of the file can be found
* **Swarm**: The collection of peers that are currently involved in downloading and uploading the pieces across the P2P network
* **Leech**: Non-seeders that do not continue to upload the pieces to other peers in the swarm

1. The first step in how torrenting works is the client device connects to the Bittorrent network and requests the file from the seed. The seed that is hosting the file will give the client one of the pieces of the file to download. If there is no seed to give the file, the download will not commence. This is why seeding is very important concept in successfully downloading a file via Bittorent. Note that the seed hosting the file only has to make one copy available at the minimum. In a client server model, the website may have to host the file on many different servers to load balance where traffic is going to. This is costly, whereas the Bittorent method is cheaper overall. 

2. The next step is that the client device will then check the tracker to see where other pieces of the file are, and will try to communicate with other peers in network to grab the remaining pieces over time. Not only is the device downloading pieces of data from its peers, it is also uploading pieces of the file it has to other peers simultaneously. This is why P2P networks are effective. If all the peers in the swarm are consistently downloading and uploading parts of the file, everyone in the swarm benefits. 

3. Once the client device has finished downloading the file entirely, it can continue to still upload the file in pieces. This device will now become a seeder, which can distribute the pieces more efficiently to other peers. Seeding can make or break a particular file download. The more people are seeding the file, the faster the whole process is. If the client device chooses to stop seeding, they become leechers. If there are more leechers than seeders for a torrent, the download will potentially be slower.

As a small example, let's suppose our 4 computers above in the screenshot were all part of a torrent download. Peer 1 completes the download and is now added to the list of seeders, while Peers 2-4 are still downloading the file. The download speed for those peers rises significantly because they now have Peer 1 to distribute the entire file. If Peer 1 quits uploading, Peers 2-4 now don't have the means to get the file from another source, and have to rely on the original seed (some client somewhere) to once again give them the remaining pieces. 

At a very high level, this is the process that Bittorent goes through in order for you to get the file you need. The entire protocol is based on the symbiotic relationship needed between peers in order to be most efficient. It only works well if everyone contributes. "The more the merrier" I guess is the right phrase to label this concept. 








