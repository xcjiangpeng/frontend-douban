<template lang="jade">
#index-sns
  .wapper
    a(href='#').homepage-top
    index-more(title='热点内容', link='https://www.baidu.com/')
    .side.index-side-w
      .yike
        a(target='_blank', :target='sns.yike.link')
          img(style='width:265px', :src="sns.yike.pic")
      index-more(title='线上活动', link='https://www.baidu.com/')
      .online
        ul
          li.size12(v-for='online in sns.onlines')
            a.title.a-link(:href='online.link') {{online.title}}
            p.time {{online.time}}
            p.num {{online.desc}}
    .main
      .albums
        ul
          li(v-for='album in sns.albums').size12
            .pic
              a(:href='album.link')
                img(:src='album.pic', alt='')
              a.a-link {{album.title}}
              span.num {{album.num}}
      .notes
         ul
          li.size12(v-for='note in sns.notes')
            a.a-link(:href='note.link') {{note.title}}
            p.author(v-if='note.desc') {{note.author}}
            p.desc(v-if='note.desc') {{note.desc}}
</template>

<script>
import IndexMore from './IndexMore'
export default {

  name: 'index-sns',

  components: {
    'index-more': IndexMore
  },

  props: ['sns'],

  data () {
    return {
    }
  }
}
</script>

<style lang='scss' scoped>
#index-sns {
  color: #999;
}

.homepage-top {
  display: block;
  background-image: url('../../assets/index-homepage-top.png');
  height: 90px;
  width: 100%;
}

.main {
  display: block;
  position: relative;
  top: -10px;
  width: calc(100% - 270px);
  min-height: 400px;
}

.albums {
  float: left;
  width: 350px;
  margin-right: 30px;
  font-size: 0;
  letter-spacing: -0.31em;
}

.albums ul {
  margin: -10px 0 0 -10px;
}

.albums ul li {
  display: inline-block;
  zoom: 1;
  letter-spacing: normal;
  word-spacing: normal;
  width: 170px;
  vertical-align: top;
  margin: 10px 0 0 10px;
}
          
.pic {
  img {
    width: 170px;
  }
  .num {
    position: relative;
    left: 5px;
  }
}

.notes ul {
  overflow: hidden;
}

.notes .desc {
  color: gray;
}

.notes li {
  line-height: 18px;
  margin-bottom: 10px; 
}

.side {
  position: relative;
  float: right;
  width: 265px;
  margin-left: 30px;
  top: -35px;
  height: 200px;
}
    
.side ul {
  position: relative;
  top: -15px;
}

.side li {
  line-height: 18px;
  margin-bottom: 10px;
}
</style>