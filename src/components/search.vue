<template>
    <div class='selectBox'>
        <select name="selects">
            <option value="">选择单位</option>
        </select>
        <select name="selects">
            <option value="">选择部门</option>
        </select>
        <select name="selects">
            <option value="">选择角色</option>
        </select>
        <input type="text" placeholder="输入关键字" class='searchInput'>
        <div class='icon iconfont icon-sousuo'></div>
        <button class='totalBtn searchBtn'>搜索</button>
        <button class='totalBtn addBtn' @click='show()'>添加</button>
    </div>
</template>

<script type="text/ecmascript-6">
export default {
  props: ['show'],
  data() {
    return {
      
    }
  }
}
</script>

<style scoped>
  .selectBox {
    display: flex;
    box-sizing: border-box;
    height: 50px;
    width: 100%;
    background-color: #e5e5e5;
    padding-left: 10px;
    align-items: center;
    margin-bottom: 12px;
  }
  .selectBox [name="selects"] {
    display: block;
    box-sizing: border-box;
    width: 160px;
    padding: 3px 2px 6px;
    color: #999;
    margin-right: 20px;
    border: 1px solid #999;
    outline: none;
  }
  .searchInput {
    box-sizing: border-box;
    width: 160px;
    height: 28px;
    border-top: 1px solid #999;
    border-left: 1px solid #999;
    border-bottom: 1px solid #999;
    border-right: 0;
    padding: 10px;
    outline: none;
    font-size: 14px;
  }
  .searchInput::-webkit-input-placeholder {
    color: #999;
    font-size: 14px;
  }
  .totalBtn {
    box-sizing: border-box;
    height: 28px;
    width: 80px;
    border: 0;
    border-radius: 5px;
    background-color: rgb(97, 6, 182);
    color: #fff;
    outline: none;
  }
  .addBtn{
    margin-left: 380px;
    background-color: #fff;
    border: 1px solid rgb(190, 189, 189);
    color: rgb(190, 189, 189);
  }
  .icon {
    box-sizing: border-box;
    width: 25px;
    height: 28px;
    background-color: #fff;
    /* margin-left: -20px; */
    text-align: center;
    line-height: 28px;
    border-top: 1px solid #999;
    border-right: 1px solid #999;
    border-bottom: 1px solid #999;
    margin-right: 20px;
    color: #999;
  }
</style>
