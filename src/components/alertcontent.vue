<template>
    <div class='alertWrap' v-show='flag2'>
      <transition name="fade" >
          <div class='alertContent' v-show='flag'>
            <div class='alertTop'>
                <div class='topLeft'>新增人员</div>
                <div class='topRight iconfont icon-anniu_guanbi' @click='closeShow()'></div>
            </div>
            <div class='alertBody'>
                <div class="item">
                    <span>单位名称:</span><span> 气象局</span>
                </div>
                <div class="item">
                    <span>部门名称:</span><span> 观测站</span>
                </div>
                <div class="item">
                    <span>人员姓名:</span>
                    <span>
                        <input type="text" v-model="name">
                    </span>
                </div>
                <div class="item">
                    <span>职务名称:</span>
                    <span>
                        <input type="text" v-model="work">
                    </span>
                </div>
                <div class="item">
                    <span>联系电话:</span>
                    <span>
                        <input type="text" v-model="tel">
                    </span>
                </div>
            </div>
            <div class='alertBtn'>
                <button class='totalBtn removeBtn' @click='closeShow()'>取消</button>
                &nbsp;
                <button class='totalBtn saveBtn' @click='commit()'>{{commitName}}</button>
            </div>
        </div>
    </transition>
  
    </div>
</template>

<script type="text/ecmascript-6">
export default {
  props: ['flag','show','flag2','itemsg','isAddCode'],
  data() {
    return {
       newName:'',
       newWork:'',
       newTel:'',
       ableFlag:true,
    }
  },
  computed: {
    commitName(){
      if(this.isAddCode){
        return '保存'
      }else{
        return '修改'
      }
    },
    name:{
      get(){
        return this.itemsg.name
      },
      set(value){
        this.newName = value
        this.ableFlag = false
      }
    },
    work:{
      get(){
        return this.itemsg.work
      },
      set(value){
        this.newWork = value
        this.ableFlag = false
      }
    },
    tel:{
      get(){
        return this.itemsg.tel
      },
      set(value){
        this.newTel = value
        this.ableFlag = false
      }
    }
  },
  methods: {
    commit(){
      if(this.isAddCode){
        this.setMsg()
      }
    },
    setMsg(){
      console.log(this.isAddCode)
      if(this.ableFlag||this.newName===this.itemsg.name&&this.newWork===this.itemsg.work&&this.newTel===this.itemsg.tel){
        alert('未修改任何数据')
        return
      }
      if(!this.newName){
        this.newName = this.itemsg.name
      }
      if(!this.newWork){
        this.newWork = this.itemsg.work
      }
      if(!this.newTel){
        this.newTel = this.itemsg.tel
      }
      var bool = confirm('确认修改此数据吗？')
      if(bool){
        this.itemsg.name = this.newName
        this.itemsg.work = this.newWork
        this.itemsg.tel = this.newTel
        this.ableFlag = true
        this.show()
      }
    },
    closeShow(){
      this.newName = this.itemsg.name
      this.newWork = this.itemsg.work
      this.newTel = this.itemsg.tel
      this.show()
    }
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
  }
  .fade-enter,.fade-leave-to{
    opacity: 0;
    transform: scale(0)
  }
  .fade-leave, .fade-enter-to {
    opacity: 1;
    transform: scale(1)
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
    outline: none
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
  .alertBtn {
    padding: 20px;
    margin-left: 120px;
  }
  .removeBtn {
    background: #e5e5e5;
  }
</style>
