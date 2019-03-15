<template>
  <div class="container">
    <x-header :right-options="{showMore: true}" :left-options="{showBack: false}">朱一龙</x-header>
    <swiper loop auto :list="img_list" :index="img_index"></swiper>
    <grid :cols="4" :show-lr-borders="false">
      <grid-item :label="('照片')" v-for="i in 4" :key="i">
        <img slot="icon" src="../assets/pigonedragon.jpg">
      </grid-item>
    </grid>
    <panel :header="'推荐'" :footer="footer" :list="list" :type="type"></panel>
  

    <tabbar>
      <tabbar-item>
        <img slot="icon" src="../assets/cake1.png">
        <span slot="label">喜欢的零食</span>
      </tabbar-item>
      <tabbar-item show-dot>
        <img slot="icon" src="../assets/patato.png">
        <span slot="label">偶像</span>
      </tabbar-item>
      <tabbar-item selected link="/component/demo">
        <img slot="icon" src="../assets/coffee.png">
        <span slot="label">饮料</span>
      </tabbar-item>
      <tabbar-item badge="2">
        <img slot="icon" src="../assets/pastry.png">
        <span slot="label">小蛋糕</span>
      </tabbar-item>
    </tabbar>
      <div>
    <p>

<a href="http://img2015.zdface.com/20190122/20b9b00b7f3eeef00f4691b33cd0af4d.jpg">
<img src="http://img2015.zdface.com/20190122/20b9b00b7f3eeef00f4691b33cd0af4d.jpg"  width="1920" height="1500" border="5">
</a>
</p>
     </div>
  </div>
  
</template>

<script>
import { Tabbar, TabbarItem, Group, Cell, XHeader, Grid, GridItem, Swiper, Panel } from 'vux'

const baseList = [{
  url: 'javascript:',
  img: 'http://pic1.win4000.com/wallpaper/2018-09-29/5baed570cf739.jpg',
  title: '这么看很帅'
}, {
  url: 'javascript:',
  img: 'http://picture.ik123.com/uploads/allimg/180728/12-1PHQ43913.jpg',
  title: '这么看依然很帅'
}, {
  url: 'javascript:',
  img: 'http://pic1.win4000.com/pic/1/9b/f9f6f5c6c9.jpg',
  title: '这么看还是很帅',
  fallbackImg: 'https://ww1.sinaimg.cn/large/663d3650gy1fq66vw50iwj20ff0aaaci.jpg'
}]

const urlList = baseList.map((item, index) => ({
  url: 'http://m.baidu.com',
  img: item.img,
  fallbackImg: item.fallbackImg,
  title: `(可点击)${item.title}`
}))

export default {
  components: {
    Panel,
    XHeader,
    Tabbar,
    TabbarItem,
    Group,
    Cell,
    Grid,
    GridItem,
    Swiper
  },
  data () {
    return {
      img_list: urlList,
      img_index: 0,
      msg: 'Hello World!',
      type: '1',
      list: [{
        src: 'http://pic1.win4000.com/pic/6/cb/37b7efa318.jpg',
        fallbackSrc: 'http://placeholder.qiniudn.com/60x60/3cc51f/ffffff',
        title: '简介',
        desc: '1988年4月16日出生于湖北武汉，中国内地男演员，毕业于北京电影学院2006级表演系本科。',
        url: '/component/cell'
      }, {
        src: 'http://dingyue.nosdn.127.net/EN2JYgbfzHRAa7WC1hzUKu03E3yNuLXS7sNr4oaYvc3XZ1539822540875.jpeg',
        title: '代表作',
        desc: '2018年6月主演奇幻网络剧《镇魂》，分饰沈巍、夜尊、黑袍使三角，凭借精湛演绎人气飙升；9月，主演年代爱情剧《许你浮生若梦》；10月，悬疑冒险剧《盗墓笔记重启》开机，饰演吴邪；12月，在电视剧《知否知否应是绿肥红瘦》中饰演小公爷齐衡。',
        url: {
          path: '/component/radio',
          replace: false
        },
        meta: {
          source: '来源信息',
          date: '时间',
          other: '其他信息'
        }
      }],
      footer: {
        title: '更多',
        url: 'http://vux.li'
      }
    }
  }
}
</script>

<style>
.container /deep/ .weui-tabbar {
  position: fixed;
}
</style>
