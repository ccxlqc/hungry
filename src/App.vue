<template>
  <div id="app">
    <v-header :seller="seller"></v-header>
    <tab></tab>
    <router-view :seller="seller"></router-view>
  </div>
</template>

<script type="text/ecmascript-6">
import header from './components/header/header.vue'
import tab from './components/tab/tab.vue'
import axios from 'axios'

const ERR_OK = 0

export default {
  data() {
    return {
      seller: {}
    }
  },
  created() {
    axios.get('/api/seller')
      .then((response) => {
        if (response.data.errno === ERR_OK) {
          // response返回的对象有data这个字段
          console.log(response)
          this.seller = response.data.data
          console.log(this.seller)
        }
      })
  },
  name: 'App',
  components: {
    'v-header': header,
    tab
  }
}
</script>
<style lang="stylus" rel="stylesheet/stylus">

</style>
