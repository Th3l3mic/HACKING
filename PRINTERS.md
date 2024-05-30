![Projekt bez nazwy](https://github.com/Th3l3mic/HACKING/assets/167564930/913dca78-fb78-4365-809f-5d14cba55d92)


<h1>Printer - hacker's best friend</h1>

<b>From the default administrator password to compromised domains </b>
<p></p>

The issue is not new, but still visible in the environment. Network administrators often neglect poorly configured network devices, such as printers. These devices can be a perfect attack vector for hackers. First, let's explain how our printers function, and then we will discuss how they can harm us by presenting the most common attack scenarios on printers.

Modern printers perform many tasks beyond printing, becoming true office warmachines. One popular functionality of a printing device is scanning a document and then sending it to a recipient in address book. The printer must authenticate itself with the domain administrator password in this process. Very often, this password is blackened on the printer page. Revealing the password may be easier than IT administrators think.
<p></p>
<img width="413" alt="printer1" src="https://github.com/Th3l3mic/HACKING/assets/167564930/dddb1c42-ad84-4b85-a33e-d26abcc6868e">

Methods of revealing the password
<p></p>
1. Some printers have a connection testing functionality, such as Kyocera office devices (as well as many others). Being on the same network, we can intercept a request from the printer using this functionality and sending the authentication to our IP address, where we have netcat listener set up. <code>netcat -l -vv -p 444</code>
<p></p>
<img width="456" alt="printer 2" src="https://github.com/Th3l3mic/HACKING/assets/167564930/ea5dd93f-16a4-413b-b46b-3fa063277005">

<p></p>
2. We can also intercept the request using a proxy server like Burp Suite during normal device usage.

Also default printer credentials, even when dont allow us to get domain admin could lead to data leaks for example: usernames. 

<b>Using the Printer Exploitation Toolkit PRET</b>

PRET is a tool created by Ruhr University in Bochum that connects to a printing device and exploits its features using one of the popular printer languages (PostScript, PJL, PCL). PRET provides huge capabilities:

- manipulating with print jobs,
- accessing memory,
- accessing the file system,
- physically damaging the device.

Each of the attacks is described in detail on the website: <a href=http://hacking-printers.net/wiki/index.php/Main_Page>Hacking_Printers</a>

Resources:

* https://www.ceos3c.com/security/obtaining-domain-credentials-printer-netcat/

* https://medium.com/@nickvangilder/exploiting-multifunction-printers-during-a-penetration-test-engagement-28d3840d8856

* https://github.com/RUB-NDS/PRET?tab=readme-ov-file

* https://grimhacker.com/2018/03/09/just-a-printer/

* http://hacking-printers.net/wiki/index.php/Main_Page

<b>Default credentials for known vendors: </b>

<code>HP 
root:password
admin:admin</code>

<code>Kyocera
Admin:Admin
admin:admin</code>

<code>Canon
administrator/
canon:canon
serial number</code>

<code>Xerox
admin:1111
serial number</code>

<code>Brother 
admin:access
admin:access123
blank</code>

<code>Epson
admin:epson
admin:admin</code>

<code>Konica Minolta
NA:12345678
NA:1234567812345678</code>

<code>RISO
Admin:3214 </code>

Stay safe!
T.
