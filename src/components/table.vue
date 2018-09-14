<template>
  <div class='tableBox'>
          <table class='tableWrap' cellpadding="0" cellspacing="0" border="0">
              <thead>
                  <tr class='tableTr'>
                      <th style='width: 5%;'>选择</th>
                      <th style='width: 8%;'>编号</th>
                      <th style='width: 8%;'>姓名</th>
                      <th style='width: 9%;'>所属单位</th>
                      <th style='width: 10%;'>部门</th>
                      <th style='width: 10%;'>职务</th>
                      <th style='width: 15%;'>联系电话</th>
                      <th style='width: 10%;'>角色</th>
                      <th style='width: 15%;'>注册时间</th>
                      <th style='width: 10%;'>操作</th>
                  </tr>
              </thead>
              <tbody>
                  <tr class='tableTr tableBody'>
                      <td style='width: 5%;'>
                          <input type="checkbox">
                      </td>
                      <td style='width: 8%;'>编号</td>
                      <td style='width: 8%;'>姓名</td>
                      <td style='width: 9%;'>所属单位</td>
                      <td style='width: 10%;'>部门</td>
                      <td style='width: 10%;'>职务</td>
                      <td style='width: 15%;'>联系电话</td>
                      <td style='width: 10%;'>角色</td>
                      <td style='width: 15%;'>注册时间</td>
                      <td style='width: 10%;'>
                          <a href="javascript:;">编辑</a>
                          &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
                          <a href="javascript:;">删除</a>
                      </td>
                  </tr>
              </tbody>
          </table>
      </div>    
</template>

<script type="text/ecmascript-6">
export default {
  data() {
    return {

    }
  },
  components: {

  }
}
</script>

<style scoped>
.tableBox,
.tableWrap {
  width: 100%;
  min-width: 1000px;
  overflow: auto;
  border-collapse: collapse;
}
.tableTr > th {
  width: 100%;
  height: 30px;
  line-height: 30px;
  background-color: rgb(200, 198, 202);
  font-size: 14px;
  font-weight: inherit;
}
.tableBody > td {
  height: 50px;
  line-height: 50px;
  text-align: center;
}
.tableTr > th,
.tableTr > td {
  border: 1px solid #999;
}
</style>
