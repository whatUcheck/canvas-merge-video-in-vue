<template>
  <div id="app">
  <merge-video :autoPlay='autoPlay' :playList='playList' :sounds='sounds' :showSounds='showSounds' :audioSrc='audioSrc' :picOption='picOption'></merge-video>
  </div>
</template>
<script>
// import Vue from 'vue'
// import MergeVideo from '../dist/canvasMergeVideo.js'
import MergeVideo from 'components/mergeVideo'
// Vue.use(MergeVideo)
export default {
  name: 'app',
  data () {
    return {
      picOption: {
        editLogo: false, // // 是否需要调整水印
        logoSrc: require('./assets/logo.png'),
        info: {
          w: 60,
          h: 60
        } // 图片信息
      },
      showContr: true,
      autoPlay: false, // 是否自动播放
      showSounds: false, // 是否展示音频控制
      playList: [],
      sounds: 0,
      audioSrc: ''
    }
  },
  components: {
    MergeVideo
  },
  mounted: function () {
    this.getData()
  },
  methods: {
    getData: function () {
      const that = this
      setTimeout(() => {
        that.playList = [{
          src: 'https://img.kuaizi.co/vid/8/3e/3ed1b8730870af30b2348f52adbc7076.mp4',
          duration: 2 // 长度
        }, { // 碎片资源列表  这个是需要后端返回的
          src: 'https://img.kuaizi.co/vid/8/fc/fc5032b1580232a1f86276601de2129d.mp4',
          duration: 1 // 长度
        }, {
          src: 'https://img.kuaizi.co/vid/8/f1/f116e8750658890deb194a1647c3b31d.mp4',
          duration: 1
        }, {
          src: 'https://img.kuaizi.co/vid/8/a6/a6160efceabdbde053cb9bc0dcca339c.mp4',
          duration: 2
        }, {
          src: 'https://img.kuaizi.co/vid/8/53/532b008e011876c6b8eff771ba773915.mp4',
          duration: 2
        }]
      }, 1000)
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.pic-adjust {
  overflow: hidden;
  width: 404px;
  margin: 0 auto;
}
.pic-adjust .wrap {
  position: relative;
  overflow: hidden;
  border: 1px solid #999;
  height: 202px;
}
</style>
