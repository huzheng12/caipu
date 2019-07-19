<template>
  <div>
    <div class="search">
      <input type="text" placeholder="搜索" v-model="keyword">
      <span @click="search">搜索</span>
    </div>



    <div v-for="(a,i) in arr" :key="i" class="nav">
      <img :src="a.albums[0]" alt="">
      <a :href="'../navTwo/main?id='+a.id" class="name">
        {{a.title}}
      </a>
      <p>
        <span>功效:&emsp;</span>{{a.tags}}
      </p>

      <p>
        <span>简介:&emsp;</span> {{a.imtro}}
      </p>
    </div>

  </div>
</template>
<script>
  export default {
    data() {
      return {
        keyword: "",
        arr: []
      }
    },
    methods: {
      search() {
        console.log(this.keyword)
        wx.request({
          url: "https://apis.juhe.cn/cook/query?key=c3d942c200256073ff822ca1dd431f16&menu=" + this.keyword, //仅为示例，并非真实的接口地址
          data: {
            x: '',
            y: ''
          },
          header: {
            'content-type': 'application/json' // 默认值
          },
          success: (res) => {
            this.arr = res.data.result.data
          }
        })
      }
    },
  }
</script>

<style>
  .search {
    display: flex;
    justify-content: space-evenly;
  }

  input {
    width: 80%;
    border: 1px solid #e0e0e0;
    border-radius: 15px;
    box-sizing: border-box;
    padding-left: 10px;
  }

  .nav {
    display: flex;
    flex-direction: column;
    align-items: center;
    border-bottom: 1px dashed #2b2b2b;
    padding-bottom: 10px;
    margin: 16px 0;
  }

  .name {
    font-size: 26px;
    font-family: 'Courier New', Courier, monospace;

  }

  .nav p {
    font-size: 20px;
    font-weight: 300;
    color: #2b2b2b;
    text-align: left;
  }

  .nav p>span {
    font-size: 26px;
    font-weight: 600;
    color: #000000;
  }
</style>