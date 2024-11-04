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
