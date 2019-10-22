---
layout: post
title:  "2019-10-22-setup_ssh_for_gitlab"
date:   2019-09-23 12:06:55 +0200
---

## generate ssh key using git bash

ssh-keygen -t rsa -C "demo@abc.com" -b 4096

## Use putty key generator to convert the primary key to putty format, assume we save the converted file to id_rsa_putty_private.ppk

## find the generated key and open the public key, copy it

## Go to gitlab 
click the right upper corner, and choose user settings->SSH keys,

Then paste the public key to add it

## in local folder
right click and choose TortoiseGit-> Setting, click GIt, and input name and email and OK

# then right click and choose Git Clone,
input the gitlab project's url, which start with git@
click load putty key, which point to "id_rsa_putty_private.ppk"

