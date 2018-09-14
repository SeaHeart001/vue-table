<template>
    <div class='alertWrap' v-show='flag'>
      <transition name="fade" >
          <div class='alertContent' v-show='flag'>
            <div class='alertTop'>
                <div class='topLeft'>新增人员</div>
                <div class='topRight iconfont icon-anniu_guanbi' @click='Show()'></div>
            </div>
            <div class='alertBody'>
                <div class="item">
                    <span>单位名称:</span><span> 水利局</span>
                </div>
                <div class="item">
                    <span>部门名称:</span><span> 水质监测科</span>
                </div>
                <div class="item">
                    <span>人员姓名:</span>
                    <span>
                        <input type="text" value='张松林'>
                    </span>
                </div>
                <div class="item">
                    <span>职务名称:</span>
                    <span>
                        <input type="text" value='科员'>
                    </span>
                </div>
                <div class="item">
                    <span>联系电话:</span>
                    <span>
                        <input type="text" value='180....4489'>
                    </span>
                </div>
            </div>
            <div class='alertBtn'>
                <button class='totalBtn removeBtn' @click='Show()'>取消</button>
                &nbsp;
                <button class='totalBtn saveBtn'>保存</button>
            </div>
        </div>
    </transition>
  
    </div>
</template>

<script type="text/ecmascript-6">
export default {
  props: ['flag','Show'],
  data() {
    return {
       
    }
  },
  methods: {
    
  },
  components: {

  }
}
</script>

<style scoped>
/* 弹出层 */
.alertWrap {
  display: flex;
  position: absolute;
  height: 100%;
  width: 100%;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: rgba(153, 153, 153, 0.6);
  justify-content: center;
  align-items: center
}
.alertContent {
  position: relative;
  width: 450px;
  height: 350px;
  background-color: #fff;
  border-radius: 5px;
}
.fade-enter-active,.fade-leave-active{
  transform-origin: 50% 50%;
  transition: all 0.5s;
  transform: scale(1)
}
.fade-enter,.fade-leave-to{
  
  transform: scale(0)
}
.alertTop {
  overflow: hidden;
  box-sizing: border-box;
  margin: 0 20px 10px;
  padding: 10px 0;
  border-bottom: 1px solid #e5e5e5;
}
.alertTop > .topLeft {
  float: left;
}
.alertTop > .topRight {
  float: right;
  font-size: 21px;
}
.item {
  margin: 15px 0 20px;
}
.item span {
  margin-left: 80px;
  font-size: 14px;
  color: #999;
}
.item span:last-of-type {
  color: #333;
}
.item span > input {
  margin-left: -10px;
  box-sizing: border-box;
  width: 150px;
  border: 1px solid #e5e5e5;
  padding: 5px 10px;
}
.totalBtn {
  box-sizing: border-box;
  height: 28px;
  width: 80px;
  border: 0;
  border-radius: 5px;
  background-color: rgb(103, 6, 182);
  color: #fff;
  outline: none;
}
.alertBtn {
  padding: 20px;
  margin-left: 120px;
}
.removeBtn {
  background: #e5e5e5;
}
</style>
