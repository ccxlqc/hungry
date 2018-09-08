<template>
  <div>
    <div>
      <star :score="2.5" :size="24"></star>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
import star from '../../components/star/star.vue'
export default{
  components: {
    star
  }
}
</script>

<style lang="stylus" rel="stylesheet/stylus">

</style>
