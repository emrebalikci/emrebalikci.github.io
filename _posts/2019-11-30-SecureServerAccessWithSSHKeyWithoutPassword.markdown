---
title:  "Secure Server Access with SSH Key without Password"
date:   2019-11-30 15:30:00
categories: [Linux, Unix]
tags: [SSH]
---
**Secure Server Access with SSH Key without Password**
You have access to many different Linux / Unix servers during the day, you are in the IT department, remembering passwords, both challenging and brings  security concerns. Inevitably, people start using the same or similar passwords after a while. Then using SSH Key to access server comes into picture. It’s fast, efficient and secure!

**1. Check if any Key Pair has already been generated**

First, we will connect to the main server via SSH (if you have direct access to the server, you can do this through the console.)

    ssh emrebalikci@main_server_host

Go to the .ssh folder to check if a private key has already been created on the server for the user you are connecting to. 

    cd ~/.ssh


If you see the id_rsa file pair in the folder, this means that the server has already created a private & public key. At this stage, you can skip the process of creating the private & public key pair and skip to step 3.


    Emres-MacBook:.ssh emrebalikci$ ls -al -rw-------    1 
    emrebalikci  staff   1679 Nov 30  2019 id_rsa -rw-r--r--    1 
    emrebalikci  staff    418 Nov 30  2019 id_rsa.pub

**2. SSH Private & Public Key Pair Creation**
While we are connected to the host server, let’s create our SSH Key pair using **ssh-keygen -t rsa** command. It will ask us to give a password to the key after the command is executed. If you leave it blank, it will not be protected with any password. If you give password, it will ask you for this password every time you want to use the SSH key pair. 



    ssh-keygen -t rsa
    Generating public/private rsa key pair.
    Enter file in which to save the key (/home/emrebalikci/.ssh/id_rsa): 
    Enter passphrase (empty for no passphrase): 
    Enter same passphrase again: 
    Your identification has been saved in /home/emrebalikci/.ssh/id_rsa.
    Your public key has been saved in /home/emrebalikci/.ssh/id_rsa.pub.
    The key fingerprint is:
    4a:dd:0a:c6:35:4e:3f:ed:27:38:8c:74:44:4d:93:67 emrebalikci@ana_sunucu
    The key's randomart image is:
    +--[ RSA 2048]----+
    |          .oo.   |
    |         .  o.E  |
    |        + .  o   |
    |     . = = .     |
    |      = S = .    |
    |     o + = +     |
    |      . o + o .  |
    |           . o   |
    |                 |
    +-----------------+

 **3. Downloading Public Key to Client Machine**

We will use the **ssh-copy-id** command on the client machine that you want to connect to the Host Server. This linux command will automatically connect to the host server and download the public SSH key to the client machine. 


    ssh-copy-id emrebalikci@main_server 
    The authenticity of host 'main_server (12.34.56.78)' can't be established. RSA key fingerprint is b1:2d:33:67:ce:35:4d:5f:f3:a8:cd:c0:c4:48:86:12.  Are you sure you want to continue connecting (yes/no)? yes Warning: Permanently added 'main_server' (RSA) to the list of known hosts. emrebalikci@main_server's password:  Now try logging into the machine, with "ssh 'emrebalikci@main_server'", and check in:   ~/.ssh/authorized_keys to make sure we haven't added extra keys that you weren't expecting. 


Above, you see the output of a successful process. After this stage, all you will do is; 

    ssh emrebalikci@main_server

You will see it does not ask for password.

Done!
