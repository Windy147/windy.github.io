`ffmpeg -i 1.rmvb -i 2.rmvb -i 3.rmvb -filter_complex "[0:v:0][0:a:0][1:v:0][1:a:0][2:v:0][
2:a:0]concat=n=3:v=1:a=1[v][a]" -map "[v]" -map "[a]" -c:v libx264 -c:a aac -movflags +faststart output.mp4
`