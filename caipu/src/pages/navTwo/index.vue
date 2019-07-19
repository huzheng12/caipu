<template>
  <div class="box">
    <div v-for="(a,i) in arr" :key="i" class="navTwo">
      <h3>{{a.title}}的做法</h3>
      <p>{{a.imtro}}</p>
      <span>{{a.title}}用料工具</span>
      <p>主料:&emsp;{{a.ingredients}}</p>
      <p>备料:&emsp;{{a.burden}}</p>
      <div>
        <span>{{a.title}}的做法:</span>
        <div v-for="(a,ind) in a.steps" :key="ind" class="zf">
         <img :src=a.img alt=""> 
          <span>{{a.step}}</span>
        </div>
      </div>
      
    </div> 
      <span>完!!!</span>
  </div>
</template>
<script>
export default {
  data() {
    return {
      arr:[]
    }
  },
  mounted() {
    const id=this.$root.$mp.query.id
    console.log(id)
    const that=this
     wx.request({
                url:"https://apis.juhe.cn/cook/queryid?key=c3d942c200256073ff822ca1dd431f16&id="+id, //仅为示例，并非真实的接口地址
                data: {
                    x: '',
                    y: ''
                },
                header: {
                    'content-type': 'application/json' // 默认值
                },
                success(res) {
                    console.log(111,res.data.result)
                    that.arr=res.data.result.data
                }
            })
 
  },
}
</script>
<style >
.box{
  padding: 0 10px 50px 10px;
}
.navTwo h3{
  display: block;
  text-align: center;
  font-size: 22px;
}
  .navTwo span{
    display: block;
    text-align: center;
    font-weight: 600;
    font-size: 20px
  }
  .navTwo p{
    text-indent: 30px;
  }
  .zf{
    display: flex;
    flex-direction: column;
    align-items: center
  }
</style>