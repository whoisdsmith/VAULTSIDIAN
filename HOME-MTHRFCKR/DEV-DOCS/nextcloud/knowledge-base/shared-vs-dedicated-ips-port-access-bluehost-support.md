---
created: 2022-08-05T09:12:36 (UTC -04:00)
tags: []
source: https://www.bluehost.com/help/article/shared-vs-dedicated-ips-port-access
author: 
---

# Shared vs. Dedicated IPs & Port Access | Bluehost Support

---
## Overview

This article will explain the differences between a Shared & Dedicated IP as well as how-to open additional ports on your account.

___

-   [Shared IP](https://www.bluehost.com/help/article/shared-vs-dedicated-ips-port-access#shared-ip)
-   [Dedicated IP](https://www.bluehost.com/help/article/shared-vs-dedicated-ips-port-access#ded-ip)
-   [Port Access](https://www.bluehost.com/help/article/shared-vs-dedicated-ips-port-access#port)
-   [Alternative Options](https://www.bluehost.com/help/article/shared-vs-dedicated-ips-port-access#alt)

___

## Shared IP

Every domain name has an IP address assigned to it. An IP address is the real address of a website or server. Domain names were developed because it is difficult to remember long IP numbers like 234.123.66.7.

In shared hosting, we host several hundred websites on one server; those same sites will share one single IP address. Instead of having a unique IP address for every domain, you share one IP address with all of the accounts on your server. The downside to shared IPs is that some countries, like China, censor particular websites by their IP address. If a website they censor is on the same server as yours, and China blocks that website using the shared IP address, then your website and the hundreds of others on that server are also blocked. This means that any clients in China would be unable to view your site. Getting a dedicated IP address would make your website separate so that if the shared IP address were blocked, your site wouldn't automatically be blocked along with it.

### Email

An email will not be affected by obtaining a dedicated IP address. Other than a program needing more than 10 minutes to send out emails from a mailing list, there is no benefit to email between a shared and a dedicated IP address. All email, including forwarded email, is sent out through our mail proxy servers. Obtaining a dedicated IP address will not prevent your emails from being marked as SPAM, having an ISP block the IP of the mail proxy server, or pass a reverse DNS test for places such as AOL. People sometimes are under the wrong impression that these things will change by obtaining a dedicated IP address. They won't change.

## Dedicated IP

By [purchasing a dedicated IP](https://www.bluehost.com/help/article/how-to-purchase-a-dedicated-ip), your site is the only one on the Internet using that unique IP address. For example, if you typed http://64.233.187.99/ into your web browser's address bar, you would see Google's website come up. This is their dedicated IP address and no one else's. This is their unique address on the web that has been attached to the domain name google.com.

## Program/Script Requirements

The program or script you run on your site may require a process to run longer than 10 minutes. On a shared IP address, the process will terminate at the 10-minute mark. With a dedicated IP address, processes are allowed to run for more than 10 minutes as long as they aren't consuming too much of the server's memory, which would result in CPU throttling. CPU throttling can occur both on a shared and a dedicated IP address. Certain voice chat programs require a dedicated IP address before they can be set up and used. If you have a program that sends out emails every so many second, such as from a mailing list program like DaDa Mail, you would need to get a dedicated IP address if it will take more than 10 minutes to send out the emails.

## Port Access

In a shared hosting environment, where everyone shares the same IP, some ports must be blocked. We block access to certain ports to help avoid having security holes in the firewall and to allow us to monitor and control customers who attempt to abuse the different services that we allow to run through these ports. The majority of processes requiring specific Port Access are typically bound to the IP address they are running on.

On a shared IP, only one service could run through a specific port from that IP. We have only opened the ports for processes running on our servers (webmail, cPanel, etc.). Purchasing a dedicated IP will allow us to grant you access to the ports you need to run your specific services. This applies to both outbound and inbound connections running on non-standard ports.

With a dedicated IP address on your account, we can generally open any port over **1024**. Ports **1024** and lower are restricted and cannot be opened.

**Note:** Because of the IP address change, you may experience a period of about 6-24 hours where your site appears to be non-functional. This is the standard propagation time that is required to update your DNS throughout the world. Please note that your temporary URL will also be changed and unavailable while the Dedicated IP is installed on your account. This is normal, and you will be able to view your site by visiting your site using your new Dedicated IP within 6-24 hours.

## Alternative Options

If you don't wish to purchase a dedicated IP and private SS, you can use a PayPal shopping cart or an alternative shopping cart hosted by another company off of your site. Your main site would still be hosted with Bluehost. However, when someone goes to pay, they would be redirected to the company you choose to host your shopping cart. Most businesses and customers don't like the idea of sending or being sent to a new website address to complete transactions.

For further assistance, you may contact our [Chat Support](https://helpchat.bluehost.com/) or Phone Support via **888-401-4678**. You may also refer to our [Knowledge Base](https://www.bluehost.com/help) articles to help answer common questions and guide you through various setup, configuration, and troubleshooting steps.
