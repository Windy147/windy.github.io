```
#!/bin/bash
for file in ./*.mp4
do
        echo "file '$(basename "$file")'" >> tmp.txt
done
sort -t 'P' -k 2n tmp.txt >>input.txt
rm tmp.txt
ffmpeg -f concat -safe 0 -i input.txt -c copy output.mp4

```