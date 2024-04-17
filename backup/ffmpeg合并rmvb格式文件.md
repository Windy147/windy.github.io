`ffmpeg -i 1.rmvb -i 2.rmvb -i 3.rmvb -filter_complex "[0:v:0][0:a:0][1:v:0][1:a:0][2:v:0][
2:a:0]concat=n=3:v=1:a=1[v][a]" -map "[v]" -map "[a]" -c:v libx264 -c:a aac -movflags +faststart output.mp4
`

```
#!/bin/bash

# 设置输出文件名
output_file="merged_output.mp4"

# 查找当前目录下的所有RMVB文件，并将它们存储到数组中
rmvb_files=(*.rmvb)

# 检查是否有RMVB文件
if [ ${#rmvb_files[@]} -eq 0 ]; then
    echo "没有找到RMVB文件"
    exit 1
fi

# 初始化一个字符串，用于存储所有RMVB文件名的连接
concat_string=""

# 循环遍历RMVB文件数组，将文件名连接成一个以竖线分隔的字符串
for file in "${rmvb_files[@]}"
do
    concat_string+="|$file"
done

# 使用FFmpeg重新编码并合并所有RMVB文件到一个MP4文件
ffmpeg -i "concat:${concat_string:1}" -c:v libx264 -c:a aac -movflags +faststart "$output_file"

echo "合并完成"
```