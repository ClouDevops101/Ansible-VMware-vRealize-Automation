vRA-deploy-VM
=============

vRA-deploy-VM is a playbook that use ansible uri core module to request a VM from vRealize automation solution

![vRA-deploy-VM](http://blogs.vmware.com/management/files/2015/02/vRA-Product-Icon-Mac_0.png)


vRA-deploy-VM Can be used to make ansible request a VM in order to replace codestream vRA tool

UNDERCONSTUCTION
================
This script take 3 argument as input :
ex :

Handbrake.sh /Volume/video mkv 3600

- the folder to feetch video files
- the video file format_
- the sleep time (in seconds) between two compression
- wether or not deleting original file

When folder is processed the script sort the video file from bigger file to smaller, than compression begin with the same order

Quality specification :_

- Compression using -e x264
- audio select track -a 1,2
- Biterate -B 128
- Quality -q 20
- Audio format aac -E copy:aac
- Subtitiles -s 1,2

Versions
--------
Handbrake.sh 1.0.1


Requirement
------------

The script use the HandBrakeCLI 64 bite
You can download it in official Hanbrake web site
[HandBrakeCLI] (https://handbrake.fr/downloads2.php)


Installation
------------





```bash
    cp Handbrake.sh /usr/local/bin/ && chmod +x /usr/local/bin/Handbrake.sh
```


Just download (Like the way it used to be)

```bash
    wget -O Handbrake.sh https://raw.githubusercontent.com/LinuxArchitects/HandBrakeCli/master/Handbrake.sh
    chmod +x Handbrake.sh
```
or

```bash
    curl -Lo Handbrake.sh https://raw.githubusercontent.com/LinuxArchitects/HandBrakeCli/master/Handbrake.sh
    chmod +x Handbrake.sh
```
Usage
-----

```bash
    $      Handbrake.sh /Volume/Video_Folder mkv   3600   yes
    usage: Handbrake.sh     [arg1]          [arg2] [arg3] [arg4]

    Command line interface for compressing mkv and mp4 video file to m4v/aac Appletv ios video format
    --------------------------------------------------------------------------
    https://github.com/LinuxArchitects/HandBrakeCli

    optional arguments:
       not for yet
```
