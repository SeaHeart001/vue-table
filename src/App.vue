<template>
  <div>
    <div id='app' class='wrap'>
      <!-- 头部 -->
      <mysearch :show='show'></mysearch>
      <!-- 表格部分 -->
      <mytable :show='show' :msg='msg'></mytable>
    </div>    
    <!-- 弹出层 -->
    <alertcontent :flag='flag' :flag2='flag2' :show='show' :itemsg='itemsg'></alertcontent>
  </div>
</template>

<script type="text/ecmascript-6">
import mysearch from './components/search.vue'
import mytable from './components/table.vue'
import alertcontent from './components/alertcontent.vue'
export default {
  data() {
    return {
      flag: false,
      flag2: false,
      msg:[
            {num:'NO.yh001',work:'主任',name:'李珊',tel:'18695330061',date: '2018-8-11 12:23:31'},
            {num:'NO.yh002',work:'主任',name:'鳄鱼',tel:'18696330062',date: '2018-8-12 12:23:32'},
            {num:'NO.yh003',work:'主任',name:'陈佳',tel:'18795330063',date: '2018-8-13 12:23:33'},
            {num:'NO.yh004',work:'主任',name:'李为',tel:'18885330064',date: '2018-8-14 12:23:34'},
            {num:'NO.yh005',work:'主任',name:'骆驼',tel:'18695330065',date: '2018-8-15 12:23:35'},
            {num:'NO.yh006',work:'主任',name:'村大洼',tel:'11695330046',date: '2018-8-16 12:23:36'},
            {num:'NO.yh007',work:'主任',name:'蔷薇',tel:'18395330067',date: '2018-8-17 12:23:37'},
            {num:'NO.yh008',work:'主任',name:'刘静',tel:'18695336788',date: '2018-8-18 12:23:38'},
            {num:'NO.yh009',work:'主任',name:'豆腐',tel:'18695337079',date: '2018-8-19 12:23:39'},
            {num:'NO.yh010',work:'主任',name:'古风',tel:'18695335060',date: '2018-8-10 12:23:30'},
        ],
      itemsg:{}
    }
  },
  methods: {
    show(index){
      this.flag = !this.flag
      if(!this.flag2){
        this.flag2 = true
      }else{
        setTimeout(() => {
          this.flag2 = false
        }, 300);
      }
      this.itemsg = {}
      if(index+1){
        console.log('123')
        this.itemsg = this.msg[index]
        console.log(index,this.itemsg)
      }
    }
  },
  components: {
    mysearch,
    mytable,
    alertcontent
  }
}
</script>

<style scoped>
  .wrap {
    box-sizing: border-box;
    width: 100%;
    height: 100%;
    padding: 15px;
  }
</style>
