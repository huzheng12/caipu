<template>
    <div>

<<<<<<< HEAD
        <Fenlei></Fenlei>
=======
        <div class="flall">

            <ul>
                <li v-for="(cai,i) in caipuLIst" @click="changenum(i)" :key="i" :class="i==num?'active1':''">

                    <span :class="i==num?'active':''">{{cai.name}}</span>
                </li>

            </ul>


            <div class="right">

                <span v-for="(list,k) in caipuLIst[num].list" :key="k" class="list">
                    <a :href="'../nav/main?id='+list.id">
                        {{list.name}}
                    </a>

                </span>




            </div>

        </div>
>>>>>>> f7b3214a415c44d57458220efbdd52dae13843f0

    </div>
</template>
<!-- <script>
    import Fenlei from "@/components/fenlei.vue"
    export default {
        components: {
            Fenlei
        },
        data() {
            return {
                caipuLIst: [],
                num: 2,

            }
        },
        created() {
            const that = this
            wx.request({
                url: 'https://apis.juhe.cn/cook/category?key=c3d942c200256073ff822ca1dd431f16', //仅为示例，并非真实的接口地址
                data: {
                    x: '',
                    y: ''
                },
                header: {
                    'content-type': 'application/json' // 默认值
                },
                success(res) {
                    that.caipuLIst = res.data.result
                    console.log(that.caipuLIst, 222)
                }
            })
        },
        methods: {
            changenum(i) {
                this.num = i
            }
        },
        mounted() {
            console.log(this.caipuLIst[this.num], 1111)
        },
    }
</script>
<style scoped>
    .flall {
        display: flex;
        position: relative;
        justify-content: space-between;
    }

    .flall>ul {
        width: 30%;
        box-sizing: border-box;
        /* margin-left: 8px; */
        /* color: aliceblue; */
        text-align: center;
        height: 1100rpx;
        overflow-y: scroll;

    }

    .flall>.right {
        width: 70%;
        /* display: flex;
        flex-wrap: wrap;
        justify-content: space-between; */

    }

    .flall>ul>li {
        background-color: #e0e0e0;
        line-height: 80rpx;
    }

    .active {

        color: #f00;
        display: inline-block;
        margin-bottom: 10rpx;
        border-bottom: 1px solid #f00;
    }

    .active1 {
        background-color: #fff !important;
    }

    .list {


        display: inline-block;
        width: 33%;
        line-height: 40px;
        text-align: center;
    }

    .list-chi {
        display: block;
        width: 45%;
        background-color: #fff;
    }
<<<<<<< HEAD
</script> -->
=======
</style>
>>>>>>> f7b3214a415c44d57458220efbdd52dae13843f0
