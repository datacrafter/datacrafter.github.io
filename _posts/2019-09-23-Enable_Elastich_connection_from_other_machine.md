---
layout: post
title:  "Enable_Elastich_connection_from_other_machine"
date:   2019-09-23 12:06:55 +0200
---
## Edit file elasticsearch.yml 
vi elasticsearch.yml

## Add following line
# note only the first line is not enough
network.host: 10.0.134.84  
transport.host: localhost
transport.tcp.port: 9300

