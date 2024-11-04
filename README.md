# RFI-Remote-file-inclusion-
RFI lab

As the name of this technique suggests, a remote file inclusion occurs when a webserver points at a file, directory, etc. that is not hosted on the webserver itself. We can therefore find ways for it to execute arbitrary code :).

For example, let’s take a look at the following wordpress plugin: gwolle-1.5.3

To exploit the webserver just clone the github directory and follow the installation procedure:

```Bash
->  git clone https://github.com/vavkamil/dvwp
```
We also have to download the vulnerable version of gwolle which can be found easily in the wordpress plugins directory: https://downloads.wordpress.org/plugin/gwolle-gb.1.5.3.zip

With the help of searchsploit we can try to find an exploit (which there is ofc!)

![gwolle_exploit.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/1cfc655f-98d7-415f-8750-3f1a8ef1a365/3197af17-ff68-4293-9934-9c848a0e7a91/e35d5b81-c953-430a-abb5-0f575a13f4c5.png)
