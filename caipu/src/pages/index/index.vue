<template>
  <div>
    <div class="swiper">
      <swiper indicator-dots="true" circular="true" interval=1500 duration=1000>
        <block v-for="(img,i) in imgUrls" :key="i">
          <swiper-item style="width: 100%">
            <image :src="img" class="slide-image" width="355" height="150" />
          </swiper-item>
        </block>
      </swiper>
    </div>

    <div class="tuijian">
      <p>精品好菜</p>
      <view class="cai">
        <block v-for="(item,i) in list" :key="i">
          <a class="singel" :href="'../navTwo/main?id='+item.id">
            <img :src="item.img" alt="">
            <p>{{item.title}}</p>
            <p class="jianjie">{{item.imtro}}</p>
          </a>
        </block>
      </view>

    </div>
  </div>
</template>

<script>
  import card from '@/components/card'

  export default {
    data() {
      return {
        imgUrls: [
          require("../../images/food1.jpg"),
          require("../../images/food2.jpg")
        ],
        list: [
          {
            "id": "23948",
            "title": "川菜——豆瓣鱼",
            "imtro": "川菜总是让人喜爱，豆瓣鱼更是有鲜又香！",
            "img": "http:\/\/juheimg.oss-cn-hangzhou.aliyuncs.com\/cookbook\/t\/24\/23948_574414.jpg"
          },
          {
            "id": "23491",
            "title": "川菜经典之红油牛百叶",
            "imtro": "川菜素以取材广泛、调味多变、菜式多样著称，可谓融汇南北特点，博采众家之长，难怪博得众多粉丝。提起川菜，光是麻、辣、鲜、香四个字的简单概括，便能引得人食指大动，再看到红、光、油、亮的绝佳卖相，更加让人欲罢不能…不过，对于一些不能嗜辣的同学来说，可能一看到那些盘盘碗碗中红亮的颜色就额头冒汗、不敢下箸了… 其实，并不是所有的川菜都会辣得让人冒汗，甚至，一些看似浸满红油的菜，吃下去并没有想象那么可怕。尤其是凉菜，不仅不会如看起来那般火辣，相反，由于调入了食醋和少许白糖，入口的感觉并不刺激，入胃的感觉也很舒服。正如今天这道红油牛百叶，是一道正宗的川味凉菜，口感鲜香爽脆，红油的点缀可以使味道更加香浓，却不会过于热辣，即便是不太能吃辣同学，吃起来也会大呼过瘾的。 牛百叶是牛四个胃中的一个，即可以叫牛胃，又可以称牛肚，《本草纲目》记载：牛胃能够补中益气，解毒、养脾胃…民间有句老话叫“吃啥补啥”，小时候，每次吃东西积食了，妈妈都会让我吃鸡胗、牛肚…可以缓解肠胃的不适。 牛百叶的做法很多，可以清蒸、可以爆炒、可以涮锅、还可以生卤…但我最爱的，还是凉拌，因为这样会最大程度地保持牛百叶最原始的清爽口感，吃到最鲜嫩的牛百叶。况且，这样加工的牛百叶，清热而不伤胃，润燥而不滞脾，还可缓解这个季节最常见的口、鼻干燥等症状。 要想做最鲜嫩的牛百叶，其实一点也不难，只需一招，在焯水的时候，放入少许料酒，这样可以中和掉牛百叶中的些许腥味，吃起来口感清爽。同时，控制好焯水的时间，不能过久，否则肉质会变老，影响口感。",
            "img": "http:\/\/juheimg.oss-cn-hangzhou.aliyuncs.com\/cookbook\/t\/24\/23491_942944.jpg"
          },
          {
            "id": "7855",
            "title": "川菜鱼香肉丝",
            "imtro": "在一本古老的大众川菜菜谱中看到了这道经典的鱼香肉丝，拿出来跟大家分享一下。北方大多在鱼香肉丝中加入胡萝卜等配菜，不够正宗，川菜中用的是木耳。这道菜具有甜酸咸辣和葱姜蒜综合的鱼香味，是比较有代表性的川菜之一。",
            "img": "http:\/\/juheimg.oss-cn-hangzhou.aliyuncs.com\/cookbook\/t\/8\/7855_655278.jpg"
          },
          {
            "id": "54317",
            "title": "湘菜版蘑菇炖小鸡",
            "imtro": "竹荪，属于蘑菇中的极品，含丰富的蛋白质和微量元素，和鸡一起炖，味道极其鲜美并且能够开胃健脾和增强身体的免疫力，是不可多得的美食。在夏天，很多人因为天气而吃不下什么东西，试一试来这一碗汤，好好的进补一下吧！",
            "img": "http:\/\/juheimg.oss-cn-hangzhou.aliyuncs.com\/cookbook\/t\/55\/54317_278619.jpg"
          },
          {
            "id": "21853",
            "title": "家常菜 彩椒土豆丝",
            "imtro": "土豆是一种粮菜兼用型的蔬菜，在欧美享有“第二面包”的称号。土豆含有丰富的维生素A和维生素C以及矿物质，被誉为人类的“第二面包”。其所含的维生素是胡萝卜的2倍、大白菜的3倍、西红柿的4倍，维生素C的含量为蔬菜之最。专家们发现，在前苏联、保加利亚、厄瓜多尔等国著名的长寿之乡里，人们的主食就是马铃薯。 土豆还有减肥、抗衰老、美容等作用，土豆的做法很多，但我还是爱吃炒土豆丝，百吃不厌。",
            "img": "http:\/\/juheimg.oss-cn-hangzhou.aliyuncs.com\/cookbook\/t\/22\/21853_637446.jpg"
          },
          {
            "id": "9594",
            "title": "西餐牛排",
            "imtro": "小孩子长身体的时候可以多吃些牛肉，儿子喜欢牛排，于是我就想在家鼓捣鼓捣，因为搭配的蔬菜颜色很漂亮，儿子连蔬菜也都吃光光了呢。",
            "img": "http:\/\/juheimg.oss-cn-hangzhou.aliyuncs.com\/cookbook\/t\/10\/9594_539277.jpg"
          },
          {
            "id": "23761",
            "title": "苏菜经典之香脆油爆虾",
            "imtro": "油爆虾是苏菜的经典菜式之一，炸透的虾壳色泽红亮、红艳松脆，与虾肉若即若离。轻轻送入口中，一触即脱，舌尖立刻可以碰触到鲜嫩无比的虾肉，咸鲜微甜、风味独特，一口一个，吃起来咔咔作响，真不是一般的过瘾。爱酒的同学，此时再来一盅小酒，那就是神仙般的日子了，快哉。",
            "img": "http:\/\/juheimg.oss-cn-hangzhou.aliyuncs.com\/cookbook\/t\/24\/23761_511415.jpg"
          },
          {
            "id": "45660",
            "title": "家常菜---刀鱼炖土豆",
            "imtro": "平时的刀鱼不是煎就是炖了，今天老爸新学的一道菜，用土豆来炖，刚开始老爸做的时候还在好奇能好吃吗，当一盘子菜端上来的时候，马上就吸引了我，好香的味道，吃起来更是好吃，刀鱼煎的正是火候，土豆是面面的，有着刀鱼的香味，特别的好吃。 刀鱼：8.00元 土豆：0.24元 油：1.00元 总计：9.24元",
            "img": "http:\/\/juheimg.oss-cn-hangzhou.aliyuncs.com\/cookbook\/t\/46\/45660_327672.jpg"
          },
          {
            "id": "37386",
            "title": "烘焙之法式蒜香包",
            "imtro": "那天无聊的时候想吃那法式蒜香包,所以就走到楼下买了一个法包来试试.于是上网找了方子来试,看来效果不错喔!大家有空也可以弄来试试啊^_^...",
            "img": "http:\/\/juheimg.oss-cn-hangzhou.aliyuncs.com\/cookbook\/t\/38\/37386_407870.jpg"
          }
        ],
      }
    },
    methods: {
      goXiang() {

      }
    },
  }
</script>

<style scoped>
  .swiper {
    box-sizing: border-box;
    overflow: hidden;
    font-size: 0;
  }

  .swiper img {
    width: 100%;
  }

  .tuijian {
    box-sizing: border-box;
    width: 100%;
    height: 100%;
    margin: 25px 0;
    padding: 0 15px;
    overflow: hidden;
  }

  .tuijian>p {
    font-weight: bold;
  }

  .tuijian>.cai {
    width: 100%;
  }

  .tuijian>.cai>.singel {
    box-sizing: border-box;
    width: 100%;
    margin: 15px 0;
  }

  .singel>img {
    width: 100%;
    border-radius: 10px;
  }

  .jianjie {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    font-size: 14px;
    color: grey;
    box-sizing: border-box;
    padding: 5px 0 0 10px;
  }
</style>