#!/bin/bash
/usr/bin/aria2c --enable-rpc --rpc-listen-all --log=/var/log/aria2c.log &> /var/log/aria2c-rpc.log
