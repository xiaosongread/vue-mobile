<template>
  <div class="content-box">
    <common-header :showinput="true" :showback="false"></common-header>
    <div class="page-content">
      <div class="tab-left-box">
        <common-tab-left :list="tabList"></common-tab-left>
      </div>
    </div>
  </div>
</template>

<script>
import {mapMutations, mapGetters, mapState} from 'vuex'
import commonHeader from 'common/common-header'
import commonTabLeft from 'common/common-tab-left'
// import * as homeApi from 'api/home-api'
// import { ERR_OK } from 'config/index'
export default {
  data () {
    return {
      num: 0,
      tabList: []
    }
  },
  created() {
    for (let i = 0; i < 30; i++) {
      let obj = {}
      obj.name = `分类${i}`
      obj.id = i
      this.tabList.push(obj)
    }
  },
  methods: {
    ...mapMutations({
      setNum: 'SET_NUM'
    }),
    todetail() {
      this.$router.togo('/Home/Detail')
    }
    // login() {
    //   let params = {
    //     password: 'gs123456',
    //     storeNo: '',
    //     userName: '17326015487'
    //   }
    //   homeApi.loginUserNo(params).then((res) => {
    //     let {data} = res
    //     if (data.success === ERR_OK) {
    //       alert(data.value.token)
    //     } else {
    //     }
    //   }).catch(() => {
    //   })
    // }
  },
  components: {
    commonHeader,
    commonTabLeft
  },
  computed: {
    ...mapGetters([
      'number'
    ]),
    ...mapState({
      number: state => state.home.number
    })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
@import "~styles/index.less";
@import "~styles/variable.less";
.page-content{
  width: 80px;
  padding-bottom: 100px;
  display: flex;
}
</style>
