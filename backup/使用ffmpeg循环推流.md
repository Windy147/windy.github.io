```#!/bin/bash
while true
        do
                cd /root/aria2-downloads/
                for video in $(ls *.mp4)
                do
                ffmpeg -re -i "$video" -c:v copy -c:a aac -b:a 192k -strict -2 -f flv "rtmp://127.0.0.1/live/123"
                done
        done
```
