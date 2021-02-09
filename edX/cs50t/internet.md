# [Internet](https://cs50.harvard.edu/technology/2017/notes/2/)
## [Notes](https://cs50.harvard.edu/technology/2017/notes/2/)
### Home Network Breakdowm
### IP
### DNS
### Packets
Like the envelope, but all is used in bits.(0 and 1)
### TCP/IP
- Transmission Control Protocol slash Internet Protocol
- IP: Now among the roles that IP plays is to support addressing, and fragmentation, and a bunch of other things too.
- TCP:Among the roles that TCP plays is to ensure that packets can get to their destination.(TCP support something called sequence numbers in addition to any fragment identifiers that also allows to ensure that data gets to its intended destination.)
### Ports
- Port number
number 80 means HTTP, Hypertext Transfer Protocol(Web servers language)
HTTP response.
But now many websites is using SSL, or HTTPS, a secure connection (443)
Emails(25)
FTP, File Transfer Protocol and other Protocol have their own numeric port identifiers, and indeed that's all this number is.
### Protocols
Transaction, like culture in human shake that person's hand when they meet.
### UDP
TCP guarantee delivery but UDP not.
Real time servers like live video, movies...
### IPs in More Detail
IPv4 x.x.x.x(256x256x256x256 -> 4 billion IP addresses, 32bits)
IP version 4, or v4
IPv6 (128-bit addresses) (2^128 IP addresses)
- private IP address(most likely come from a home router, bussiness router or maybe your ISP)
addresss that starts with
10.
192.168.
172.16
### Routers
sometimes called gateway
like a table, excell.
And that table, generally has at least like two columns, one of which has an IP address or a prefix, second is where should go.
### Traceroute
traceroute  128.32.203.137
traceroute  www.berkeley.edu
we can see how many router from our home router to walk until we go to www.berkeley.edu
```shell
(base)  XF@MacBook-Pro ⮀ ~/src/justin-tse ⮀ traceroute  128.32.203.137
traceroute to 128.32.203.137 (128.32.203.137), 64 hops max, 52 byte packets
 1  192.168.1.1 (192.168.1.1)  0.931 ms  0.685 ms  0.649 ms
 2  100.64.0.1 (100.64.0.1)  21.439 ms  2.068 ms  2.153 ms
 3  113.98.88.185 (113.98.88.185)  8.671 ms  7.242 ms  7.941 ms
 4  113.98.79.9 (113.98.79.9)  9.617 ms  7.298 ms  8.055 ms
 5  202.97.94.138 (202.97.94.138)  7.769 ms  4.505 ms  4.692 ms
 6  202.97.12.13 (202.97.12.13)  5.533 ms
    202.97.94.114 (202.97.94.114)  6.318 ms
    202.97.94.98 (202.97.94.98)  15.825 ms
 7  202.97.98.181 (202.97.98.181)  162.484 ms  170.566 ms  166.103 ms
 8  202.97.50.26 (202.97.50.26)  165.713 ms
    202.97.90.118 (202.97.90.118)  167.524 ms
    202.97.50.26 (202.97.50.26)  163.665 ms
 9  xe-5-0-1.0.rtsw.wilc.net.internet2.edu (162.252.69.138)  168.051 ms  160.278 ms  157.576 ms
10  lo-0.8.rtsw.losa.net.internet2.edu (64.57.20.255)  159.600 ms  159.510 ms  159.057 ms
11  * 64.57.20.83 (64.57.20.83)  158.919 ms  158.341 ms
12  dc-svl-agg8--lax-agg8-100ge-1.cenic.net (137.164.11.1)  169.921 ms  168.839 ms  171.180 ms
13  dc-svl-agg10--svl-agg8-300g.cenic.net (137.164.11.80)  169.890 ms  169.129 ms  169.933 ms
14  dc-oak-agg8--svl-agg10-300g.cenic.net (137.164.11.95)  177.458 ms  174.109 ms *
15  ucb--oak-agg8-10g.cenic.net (137.164.50.31)  165.637 ms  168.509 ms  166.038 ms
16  reccev-cev-cr1--et-0-0-1.net.berkeley.edu (128.32.0.39)  174.754 ms
    sut-mdc-cr1--et-0-0-1.net.berkeley.edu (128.32.0.37)  165.552 ms
    reccev-cev-cr1--et-0-0-1.net.berkeley.edu (128.32.0.39)  175.023 ms
17  et3-47.inr-311-ewdc.berkeley.edu (128.32.0.103)  164.852 ms
    et3-48.inr-311-ewdc.berkeley.edu (128.32.0.101)  167.518 ms  166.649 ms
18  calweb-farm-prod.ist.berkeley.edu (128.32.203.137)  166.287 ms  170.512 ms  167.068 ms
```
```shell
(base)  ✘ XF@MacBook-Pro ⮀ ~/src/justin-tse ⮀ traceroute 140.247.2.33 
traceroute to 140.247.2.33 (140.247.2.33), 64 hops max, 52 byte packets
 1  192.168.1.1 (192.168.1.1)  0.948 ms  0.507 ms  0.576 ms
 2  100.64.0.1 (100.64.0.1)  10.912 ms  2.243 ms  2.184 ms
 3  113.98.78.97 (113.98.78.97)  7.161 ms  7.236 ms  8.102 ms
 4  113.98.78.245 (113.98.78.245)  7.533 ms  7.180 ms  7.946 ms
 5  202.97.94.126 (202.97.94.126)  4.413 ms  4.511 ms  4.590 ms
 6  202.97.12.1 (202.97.12.1)  4.987 ms
    202.97.12.25 (202.97.12.25)  18.922 ms
    202.97.12.17 (202.97.12.17)  5.618 ms
 7  202.97.46.182 (202.97.46.182)  166.901 ms  164.295 ms
    202.97.52.222 (202.97.52.222)  166.140 ms
 8  202.97.90.114 (202.97.90.114)  164.238 ms
    202.97.86.177 (202.97.86.177)  172.029 ms
    202.97.50.30 (202.97.50.30)  164.689 ms
 9  * * *
10  be3670.ccr22.sfo01.atlas.cogentco.com (154.54.43.13)  189.716 ms * *
11  president-a.edge2.newyork6.level3.net (4.31.157.126)  248.639 ms  249.632 ms
    be3110.ccr32.slc01.atlas.cogentco.com (154.54.44.142)  179.103 ms
12  core-ne-gw-vl408.fas.harvard.edu (140.247.2.33)  260.767 ms
    be3038.ccr22.den01.atlas.cogentco.com (154.54.42.98)  204.063 ms
    core-ne-gw-vl408.fas.harvard.edu (140.247.2.33)  252.007 ms
```


```shell
(base)  XF@MacBook-Pro ⮀ ~/src/justin-tse ⮀ traceroute www.cnn.co.jp
traceroute: Warning: www.cnn.co.jp has multiple addresses; using 101.102.235.200
traceroute to cdnext-svg001-ipb001.stream.ne.jp (101.102.235.200), 64 hops max, 52 byte packets
 1  192.168.1.1 (192.168.1.1)  1.129 ms  0.604 ms  0.576 ms
 2  100.64.0.1 (100.64.0.1)  24.987 ms  2.048 ms  2.070 ms
 3  113.98.81.17 (113.98.81.17)  9.664 ms  7.167 ms  8.001 ms
 4  113.98.79.13 (113.98.79.13)  9.180 ms  8.805 ms  7.958 ms
 5  202.97.82.85 (202.97.82.85)  31.700 ms  33.737 ms  32.098 ms
 6  202.97.50.158 (202.97.50.158)  41.438 ms  45.523 ms  43.408 ms
 7  202.97.51.241 (202.97.51.241)  33.059 ms  31.432 ms  32.080 ms
 8  softbank221111202049.bbtec.net (221.111.202.49)  62.371 ms  52.850 ms  56.268 ms
 9  * * *
10  118.103.120.178 (118.103.120.178)  69.052 ms  75.297 ms  73.932 ms
11  101.102.235.200 (101.102.235.200)  71.720 ms  72.712 ms  73.683 ms
```


### Undersea Cabling
### Cable Modern Demo
RJ11 telephone
RJ45 jacks internet cable
WiFi
DNS DHCP
### Network Switch Demo
For example, One RJ45 jack to share more RJ45 jacks
### Home Router Demo
Router
### Network Cable Demo
Have different color wires, some of them are used for transmission, some of them are used for receiving, some of them are used for not technically, which used for insulation and cancellation of what might otherwise be interference.
### Closing Thoughts and Homework


### Assignments
1.In a sentence that a non-technical friend or family member would understand, what is the internet?

Internet is a tool which can let you use your computer to communicate with different people in different places in the world.


2.What does it mean if a URL begins with https:// as opposed to http://? 如果 URL 以 https://开头，而不是以 http://开头，这意味着什么？

URL begins HTTP means it is using hypertext text transfer protocol, port 80.  HTTPS means it is HTTP and also using SSL, a secure connection, port 443.

3.What does a DHCP server do? DHCP 服务器做什么？

DHCP server is used to 


4.What is the purpose of a subnet mask? 子网掩码的用途是什么？



5.Recall that TCP (tries to) guarantee delivery by ensuring that any lost packets are resent. Why, though, might packets be lost between a sender and receiver? 回想一下，TCP (试图)通过确保重发丢失的数据包来保证传输。但是，为什么数据包会在发送方和接收方之间丢失呢？

6.Describe the difference between a cable modem and a router, in the context of home networking. 描述在家庭网络环境下，电缆调制解调器和路由器的区别

7.In what sense are domain names similar to phone numbers like 1-800-COLLECT? 域名在什么意义上类似于电话号码1-800-COLLECT？

8.What is a "protocol"? 什么是“协议”？



9.What problem is IPv6 attempting to solve? IPv6试图解决什么问题？

IPv4 uses 32 bits  IP address that we can only contain about 4.3 billion different IP address. But when more and more devices are used to connect to the Internet. We have more than 7 billion people and many people have more than one device.  So 4.3 billion is not enough for us to use. However, IPv6 uses 128 bits IP address, so we can contain about  2^128 different IP address. Therefore, we can solve this problem the more and more devices need to connect the Internet.

10.What elements make up a "packet"? 什么元素组成了“数据包”？



- traceroute
```shell
(base)  ✘ XF@MacBook-Pro ⮀ ~/src/justin-tse/app-academy ⮀ ⭠ master± ⮀ traceroute 128.32.203.137
traceroute to 128.32.203.137 (128.32.203.137), 64 hops max, 52 byte packets
 1  192.168.1.1 (192.168.1.1)  0.928 ms  0.576 ms  0.486 ms
 2  100.64.0.1 (100.64.0.1)  1.806 ms  1.678 ms  1.419 ms
 3  113.98.81.1 (113.98.81.1)  10.133 ms  8.362 ms  7.962 ms
 4  113.98.78.249 (113.98.78.249)  6.134 ms  9.438 ms  7.871 ms
 5  202.97.94.122 (202.97.94.122)  5.705 ms  4.211 ms  4.609 ms
 6  202.97.12.9 (202.97.12.9)  5.154 ms
    202.97.12.41 (202.97.12.41)  15.882 ms
    202.97.12.17 (202.97.12.17)  4.909 ms
 7  202.97.99.218 (202.97.99.218)  175.919 ms
    202.97.58.214 (202.97.58.214)  165.690 ms
    202.97.45.246 (202.97.45.246)  170.446 ms
 8  202.97.92.45 (202.97.92.45)  174.391 ms  171.932 ms
    202.97.50.30 (202.97.50.30)  173.234 ms
 9  xe-5-0-1.0.rtsw.wilc.net.internet2.edu (162.252.69.138)  167.804 ms  173.570 ms  160.773 ms
10  lo-0.8.rtsw.losa.net.internet2.edu (64.57.20.255)  166.614 ms  166.149 ms  164.986 ms
11  64.57.20.83 (64.57.20.83)  167.768 ms  170.163 ms  171.700 ms
12  dc-svl-agg8--lax-agg8-100ge-1.cenic.net (137.164.11.1)  176.285 ms *  178.280 ms
13  dc-svl-agg10--svl-agg8-300g.cenic.net (137.164.11.80)  178.484 ms  170.400 ms  167.604 ms
14  dc-oak-agg8--svl-agg10-300g.cenic.net (137.164.11.95)  170.077 ms *  173.302 ms
15  ucb--oak-agg8-10g.cenic.net (137.164.50.31)  178.115 ms  175.820 ms  175.636 ms
16  sut-mdc-cr1--et-0-0-1.net.berkeley.edu (128.32.0.37)  172.777 ms
    reccev-cev-cr1--et-0-0-1.net.berkeley.edu (128.32.0.39)  183.486 ms
    sut-mdc-cr1--et-0-0-1.net.berkeley.edu (128.32.0.37)  178.998 ms
17  et3-48.inr-311-ewdc.berkeley.edu (128.32.0.101)  175.439 ms  175.867 ms
    e3-47.inr-310-ewdc.berkeley.edu (128.32.0.99)  170.774 ms
18  calweb-farm-prod.ist.berkeley.edu (128.32.203.137)  173.042 ms  165.580 ms *
```

1. 128.32.203.137
Decimal: 2149632905

Hostname: calweb-farm-prod.ist.berkeley.edu

ASN: 25

ISP: University of California at Berkeley

Organization: University of California at Berkeley

Services: None detected

Type: Broadband

Assignment: Likely Static IP

Continent: North America

Country: United States

State/Region: California

City: Oakland

Javascript disabled or geolocation map not available.
+
-
Leaflet | © OpenStreetMap Terms
Latitude: 37.8381  (37° 50′ 17.16″ N)

Longitude: -122.2609  (122° 15′ 39.24″ W)

Postal Code: 94609

