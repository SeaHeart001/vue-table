<template>
  <div>
    <div id='app' class='wrap'>
      <!-- 头部 -->
      <mysearch :show='show'></mysearch>
      <!-- 表格部分 -->
      <mytable></mytable>
    </div>    
    <!-- 弹出层 -->
    <alertcontent :flag='flag' :show='show'></alertcontent>
  </div>
</template>

<script type="text/ecmascript-6">
import mysearch from './components/search.vue'
import mytable from './components/table.vue'
import alertcontent from './components/alertcontent.vue'
export default {
  data() {
    return {
      flag: false
    }
  },
  methods: {
    show(){
      this.flag = !this.flag
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
