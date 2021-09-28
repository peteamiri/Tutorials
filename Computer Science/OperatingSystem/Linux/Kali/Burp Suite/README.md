# Burp suite

This is tutorial deals with Burp Suite on Kali Linux. Burp Suite is used for security testing for network intrusion, especially web applications. This tool is available by default on a variety of security operating systems such as Kali Linux.

Burp proxy allows to intercept the traffic between the browser and target application. This option works in similar fashion to the man-in-the-middle attack vector. To demonstrate this feature, consider the following example of a Wikipedia login
form (dummyuser:dummypassword) as shown in Figure 2. First, switch the intercept mode “on” in the suite. The Forward option allows you to send the packets from the source IP to the destination IP. The Drop option allows you to drop the packet if you feel
it does not need analysis.

to start the burp suite type `burpsuite` on command line.

## Burp Suite plugins

### AdminPanelFinder plugin
This plugin is for searching the admin pages of a website. Using this plugin, you can easily find the website admin panel in burpsuite. Among the features of this plugin, you can test more than 1000 pages and its high speed.

### Backup Finder plugin
This plugin is for searching backup files inside the server, which is used as a plugin in burpsuite. It also has the ability to read directories and search for backups using default names.

### BurpelFish Translator plugin
This plugin is excellent and useful and translates foreign texts using Google when testing penetration. Due to the use of Google service, you can translate all common languages.

### AES Killer plugin
This plugin is for breaking AES encryption when traffic passes through the network and is very useful for testing the penetration of encrypted data. It also has the ability to connect to a proxy and scan.

### Burp WP plugin Burp WP
To search for WordPress plugins using burpsuite which has the ability to search more than 35,000 WordPress plugins.
