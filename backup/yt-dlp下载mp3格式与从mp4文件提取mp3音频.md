yt-dlp --extract-audio --audio-format mp3 $1
ffmpeg -i $1 -vn -acodec libmp3lame -q:a 0 $2
