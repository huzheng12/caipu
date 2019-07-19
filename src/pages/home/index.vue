<template>
    <div>

        <Fenlei></Fenlei>

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

            }
        },
        created() {
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
                    console.log(res.data)
                }
            })
        }
    }
</script> -->