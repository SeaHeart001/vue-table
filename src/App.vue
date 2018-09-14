<template>
  <div>
    <div id='app' class='wrap'>
      <!-- 头部 -->
      <mysearch :Show='Show'></mysearch>
      <!-- 表格部分 -->
      <mytable></mytable>
    </div>    
    <!-- 弹出层 -->
    <alertcontent :flag='flag' :Show='Show'></alertcontent>
  </div>
</template>

<script type="text/ecmascript-6">
import mysearch from './components/search.vue'
import mytable from './components/table.vue'
import alertcontent from './components/alertcontent.vue'
export default {
  data() {
    return {
      flag:false
    };
  },
  methods: {
    Show(){
      this.flag = !this.flag
    }
  },
  components: {
    mysearch,
    mytable,
    alertcontent
  }
};
</script>

<style scoped>
/* reset */
* {
  margin: 0;
  padding: 0;
}
a {
  text-decoration: none;
}
html,
body {
  width: 100%;
  height: 100%;
}
input,
button {
  border: 0;
  outline: none;
}
/* reset */
.wrap {
  box-sizing: border-box;
  width: 100%;
  height: 100%;
  padding: 15px;
}

</style>
