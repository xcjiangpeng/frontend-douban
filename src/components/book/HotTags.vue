<template lang="jade">
.hot-tags.section
  .hd
    span 热门标签
    a(href='https://book.douban.com/latest?icn=index-latestbook-all') 所有热门标签»
  .bd
    ul
      li(v-for='0 in 4')
        ul.section
          li(v-for='0 in 10')
            a {{$index}}{{$index}}{{$index}}
</template>

<script>
export default {

  name: 'hot-tags',

  data () {
    return {

    }
  }
}
</script>

<style lang="scss" scoped>

@import "../../assets/book.scss";

.hot-tags  {
  margin-top: 30px;
}

.hot-tags .bd .section {
  margin-bottom: 15px;
}

.hot-tags .bd .section li {
  display: inline-block;
}

.hot-tags .bd .section li {
  padding: 2px 11px 0;
  margin: 0 3px 5px 0;
  line-height: 20px;
  font-size: 13px;
  background-color: #f5f5f5;
}

.hot-tags .bd .section li:first-child a {
  color: black;
  cursor: text;
}

.hot-tags .bd .section li:first-child {
  display: block;
  background-color: white;
}

.hot-tags .bd .section li:first-child:hover {
  background-color: white;
}

.hot-tags .bd .section li:hover {
  background-color: #E4E4E4;
}

.hot-tags .bd .section li:last-child a {
  color: gray;
  padding-right: 10px;
}
</style>