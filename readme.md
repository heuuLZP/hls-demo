## 如何运行

下载本项目到本地，建议通过 `http-server` 启动一个静态服务器，然后 `charles` 代理，就可以在移动端访问了。

## 视频资源

视频资源太大了，只保留一个ts 切片文件也上传不到 git ，建议自己找个 mp4 通过 ffmpeg 进行分片。

```

ffmpeg -i test.mp4 -c copy -start_number 0 -hls_time 5 -hls_list_size 0 -hls_segment_filename test%03d.ts index.m3u8
```

然后把切片资源放到 video 目录即可

## html 说明

- index.html 
  这个包含完整交互，但是只支持 `微信`、`移动端Chrome`、`safari`、`uc`、`qq` 浏览器

- hls.html
  通过 `hls.js` 支持 在 `pc Chrome` 中播放

- video.html
  通过 `video.js` 支持在 `pc chrome` 中播放