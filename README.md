# v-dplayer
一个基于Dplayer的Vue2插件

# 安装
```
npm install v-dplayer --save
或
cnpm insatll v-dplayer --save
```

# 使用
- 在main.js中添加
```JavaScript
import VDplayer from 'v-dplayer'
import '../node_modules/v-dplayer/dist/style.css'

Vue.use(VDplayer)
```
- 在Vue组件中使用
```JavaScript
<template>
  <div id="app">
    <v-dplayer :options=options id="dplayer"></v-dplayer>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      options: {
        autoplay: false,
        theme: '#FADFA3',
        loop: true,
        lang: 'zh-cn',
        screenshot: true,
        hotkey: true,
        preload: 'auto',
        logo: 'logo.png',
        volume: 0.7,
        mutex: true,
        video: {
            url: 'dplayer.mp4',
            pic: 'dplayer.png',
            thumbnails: 'thumbnails.jpg',
            type: 'auto'
        },
        subtitle: {
            url: 'dplayer.vtt',
            type: 'webvtt',
            fontSize: '25px',
            bottom: '10%',
            color: '#b7daff'
        },
        danmaku: {
            id: '9E2E3368B56CDBB4',
            api: 'https://api.prprpr.me/dplayer/',
            token: 'tokendemo',
            maximum: 1000,
            addition: ['https://api.prprpr.me/dplayer/bilibili?aid=4157142'],
            user: 'DIYgod',
            bottom: '15%',
            unlimited: true
        },
        contextmenu: [
            {
                text: 'custom1',
                link: 'https://github.com/DIYgod/DPlayer'
            },
            {
                text: 'custom2',
                click: (player) => {
                    console.log(player);
                }
            }
        ]
      }
    }
  }
}
</script>

<style>
#dplayer {
  width: 1024px;
  height: 500px;
  margin: 0 auto;
}
</style>
```