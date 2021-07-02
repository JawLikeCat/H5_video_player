# H5_video_player
基于video.js实现无flash插件播放.m3u8直播流
1.使用方法

    将video.js下载到html目录下，并在html中引用video-js.css与video.js
    
2.举例index.html

    <!DOCTYPE html>
    <html lang="en">
      <head>
        <meta charset="UTF-8">
        <title>videoJs</title>
 
                  <link href="./video.js/video-js.css" rel="stylesheet" />
                
                  <!-- If you'd like to support IE8 (for Video.js versions prior to v7) -->
                  <script src="./video.js/videojs-ie8.min.js"></script>
      </head>
      <body>
        <section id="videoPlayer">
            <video id="my-video" width="600" height="300" class="video-js vjs-default-skin vjs-big-play-centered" poster="">
                <source src="./hls/test1_0.m3u8" type="application/x-mpegURL" id="target">

            </video>
        </section>
                  <script src="./video.js/video.js"></script>
        <script type="text/javascript">
            var player = videojs('my-video', { "poster": "", "controls": "true" }, function() {
                this.on('play', function() {
                    console.log('正在播放');
                });
                //暂停--播放完毕后也会暂停
                this.on('pause', function() {
                    console.log("暂停中")
                });
                // 结束
                this.on('ended', function() {
                    console.log('结束');
                })
 
            });
