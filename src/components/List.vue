<template>
  <div class="list">
    <a :href="item.src_url" class="weui-media-box weui-media-box_appmsg"  v-for="item in listData">
      <div class="weui-media-box__hd">
      </div>
      <div class="weui-media-box__bd">
        <h4 class="weui-media-box__title">{{item.title}}</h4>
        <p class="weui-media-box__desc">{{item.author}}</p>
        <p class="weui-media-box__time">{{item.created_at}}</p>
      </div>
    </a>
  </div>
</template>

<script>
  import { bus } from '../bus.js'
  export default {
    name: 'list',
    data () {
      return {
        listData: [],
        tip: '0'
      }
    },
    created () {
      bus.$on('tip', (text) => {
        this.tip = text
        this.getLists(text)
      })
    },
    methods: {
      getLists: function (id) {
        this.$http.post('/api/channel/' + id, {id: id}).then((response) => {
          this.listData = response.body
        })
      }
    }
  }
</script>
