<template>
    <ul class="tab-left">
      <li v-for="(item, index) in list" :key='index' class="tab-left-item">{{item.name}}</li>
    </ul>
</template>

<script>
export default {
  data() {
    return {}
  },
  props: {
    list: {
      type: Array,
      default: function() {
        return []
      }
    }
  },
  methods: {
    back() {
      this.$router.goBack()
    }
  },
  components: {

  }
}
</script>

<style lang="less" scoped>
@import "~styles/index.less";
.tab-left{
  width: 80px;
  min-height: 100%;
  background: #f8f8f8;
  .tab-left-item{
    line-height: 40px;
    text-align: center;
    font-size: 14px;
    &.active{
      background: #ffffff;
    }
  }
}
</style>
