---
layout: post
title:  "2019-10-29-setup_remote_for_vscode_withoutinternetaccess"
date:   2019-10-29 12:06:55 +0200
---
## Generate key pair, assume
private key is quickstart.pem and public key is quickstart.pub

## Remote development
1. Create  file vscodessh_config with following content and put in the location D:\zTools\putty\vscodessh_config
    Host ec2_elastic_stack
    User centos
    HostName 10.0.134.84
    IdentityFile D:\zTools\putty\quickstart.pem
2. CTRL+SHIFT+P and choose Remote-SSH: Connect to Host, then select Config SSH Host->Settings, update the setting with the path mentioned in step 1
3. Close the window, reload the vscode 


## Put public key in server
ssh-copy-id -i ~/quickstart user@92.168.0.10

## Install remote wihout internet access
When you connect to a host it executes a bash script that wgets or curls a tarball and extracts it in a directory in your home directory. Here's an offline workaround.

1. Attempt to connect, let it fail
    On server, get the commit id

    $ ls ~/.vscode-server/bin
    553cfb2c2205db5f15f3ee8395bbd5cf066d357d
2. 
    Download tarball replacing $COMMIT_ID with the the commit number from the previous step https://update.code.visualstudio.com/commit:$COMMIT_ID/server-linux-x64/stable
    e.g.;
    https://update.code.visualstudio.com/commit:6ab598523be7a800d7f3eb4d92d7ab9a66069390/server-linux-x64/stable
3. 
    Move tarball to ~/.vscode-server/bin/$COMMIT_ID/vscode-server-linux-x64.tar.gz

4. 
    Extract tarball in this directory

    $ cd ~/.vscode-server/bin/$COMMIT_ID
    $ tar -xvzf vscode-server-linux-x64.tar.gz --strip-components 1
    Connect again

