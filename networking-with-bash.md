Hello, young lad (or gal).

So you ought to learn some networking with bash, eh?

Worry not - I've already prepared some useful commands for you.

If you want to check network interfaces your device has, use `ifconfig`.

If that's a first time you use this command - take your time. Slowly look through all the output you got. You can find your network ID address (inet), netmask, and broadcast address. You can find here more than one interface.

How exciting, right?

(For wireless network interfaces use `iwconfig`).

Let's say you want to change your IP address. How would you do that?

Well you do it like this: `ifconfig [name of a network iterface] [IP address you want to have]`

Yeah, but when you use ifconfig, there are more information than IP address, right? You can find there netmask and broadcast as well, right?

You can change them as well:

`ifconfig [name of a network interface] [IP address] netmask [netmask address] broadcast [broadcast address]`.

Okay, it all looks cool and funny, but changing IP address is simply not enough to fool other devices - packets your device sends contain your MAC address as well.

'Well, so how do I change my MAC adress?' - hopefully you asked

That's a bit tricky, because you have to take your chosen network interface down, to actually change its MAC address.

And you do this like this:

```
ifconfig [name of a network interface] down
ifconfig [name of a network interface] hw ether [your chosen MAC address]
ifconfig [name of a network interface] up
```

So hopefully you know a thing or two about DNS (you do, right?).

So let's say there is your favourite website. And you want to check its nameserver.

You do it like this: `dig [the url] ns`

You wanna check out exchange? No problem: `dig [the url] mx`

If you want to change your default DNS server you can edit this file: `/etc/resolv.conf`

And there is another cool trick you can use - there is a file that is checked before reaching any DNS server - `/etc/hosts`

Play with those commands on your station - be careful though, you can mess up your internet connection.

Have fun!
