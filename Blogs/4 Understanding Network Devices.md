---
tags:
  - Blogs
---
What solution comes to mind when the internet stops working. Probably to restart the router, right ?. If you were born before the early 2000, you will probably remember there being two routers one with an antenna and one without one. The one without the antenna is called a modem and the one with the antenna is called a router. Nowadays you have a router that has modem built in it, or if you use optical fiber for the internet, modem is not required at all, so the newer generation of people aren't familiar with the word modem.

So the question may arise in your mind what is a modem and a router ?
A modem is basically a device that converts digital signals that is understood by our computers into analog signal that is more efficient for transmission and vice versa. You needed this in the past as the router didn't understand analog signal and the coaxial cable used for transmitting the data back in the day only supported analog transmission. So modem was basically a translating device for the router and the cable infrastructure.

**Routers**: The miracle box that makes the internet work in your device. It works like a postman but for digital packages. It reads the address on the package (IP address on the header of the data package) and then determines which device is the ultimate destination for the package. And sends the package to the device either wirelessly or if its connected via ethernet cable, then via the wired route. It is able to do 

**Break-Down of how router knows device to transfer the package to**

![[images/3.png]]![[images/4.png]]

Now lets dive Into Switches and Hubs
Switches and Hubs are two types of device that are used for similar work that is to increase the number of device connected to the network via wires. Generally via ethernet cable and RJ45 jack. Although they have the same task they do have some important differences they are :

**Switches**
- Sends packages to the individual device according to their mac address
- More efficient compared to hub
- More secured compared to hub
**Hub**
- Sends packages to all the devices in the network
- Less efficient and less secured compared to switch
- More affordable compared to switch

**FireWall**
Like the name suggests firewall is a barrier between the internet and you home network or computer. Traditionally it used to be an actual hardware that used to scan each and every package for malicious code or a malicious sender. Nowadays a software is used which runs either on the router level or the actual device level.
Firewall responsibility is to protect the end user from the malicious  actors from the internet.

**Load Balancers**
Imagine you are deploying your next big project **Tinder but for dogs**. Its a huge success and you have hundreds of millions of users. You can only process so much request from a single computer  as a server. You may thinking of increasing the capacity of the server by adding extra ram, storage or even upgrading the processor **(Vertical Scaling)** . But at a point in time you will realize this is to expensive and is not feasible. The next solution is to spin up another computer now u have double the capacity of handling request **(Horizontal Scaling)** . But you will need a mechanism to ensure that the requests are divided into the multiple server instances so you  wont have one server running at  maximum capacity and the other one hardly getting any traffic.

To solve this issue load Balancers are user. They are responsible for distributing traffic among the available serve instances. And ensuring that each server instance is healthy. Incase of error it redirects traffic to other healthy server instances.

**Conclusion**
In real world scenario all these technologies work together to ensure that the internet functions and you can enjoy you cat videos in youtube without a hacker getting your bank details or social security info. When u click on that cat video the request goes from Your device -> switch/ hub -> router -> modem -> global network of optical fiber and satellites -> youtube servers -> load balancers -> actual device that process the request 
Then the response travels back all the way from the same path back to your modem -> router -> firewall and finally your Device so you can enjoy your cat videos.