

<template>
      <div class="group">
        <div class="mainimg">
        <img src="../assets/death.gif"  alt="稍等">
        
        </div>
        <div class="textbox">
          <div v-for="(id,item) in data.fans" v-if="data.showthis" class="textin">
            <p >{{item}} Number of fans:{{id}}</p> 
          </div>
        </div>
       </div>
       <p class="text2">“首先，无论如何，5-1=0。 当珈乐离去，缺失了一角，这不仅仅是一个成员的离去，这是五位姑娘共同的梦的破碎!今晚的直播，毫无疑问打碎了最后一点幻想。要么当提线木偶，要么鱼死网破。粉丝分化、内斗，毫无疑问这正是运营想看到的。

其次，我们是弱势方!!

在什么都没做的情况下，运营的任何保障都是毫无效力的!!!

如果我们在这样的关头不团结起来，在二十号之前不做点什么的话，那才是真正的无可挽回!!

有很多小伙伴会问，那其余四位小姐姐呢?关于这点，我明确告诉你们，没有比现在更坏的情况了。如果我们无动于衷，就此接受命运欺骗自己，那么接下来就是被吸血，被压榨的命运，鸟巢?追梦?今晚的事实摆在你面前了!别再对这个企划抱有希望了!根本不可能!再待下去，只能是等死!还要受各种压榨! 无论如何，我们必须冲下去，必须扩大化，这是我们唯一的筹码和武器。

最后，我衷心的呼吁全体- -个魂，全体反A雅士：无论你是谁，只要你愿意给A-SOUL一刀，请加入我们!”
</p>
 
        <div v-if="!data.showthis">加载中</div>
 



</template>

<script setup>
import { ref } from 'vue'
import axios from "axios"
import { defineAsyncComponent } from "vue";
import { onMounted, reactive } from "vue";
// defineProps({
//   msg: String
// })
const data = reactive({
  showthis:false,
  fans:{},
  obj:{'嘉然':"672328094","珈乐":"351609538","乃琳":"672342685","向晚":"672346917","贝拉":"672353429","asoul":"703007996"}
})

onMounted(async()=>{
  // this.$nextTick(() => {
  // console.log('/api/node/v1/asoul-data/allFansData?time=1652323803989&range=1')
  // `/api/node/v1/asoul-data/allFansData?time=${new Date().getTime()}&range=1`
  // let 
  for(let i in data.obj){
  axios.get('http://124.222.1.223/x/web-interface/card', { params: { mid: data.obj[i] } })
  .then(function (response) {
    data.fans[i]=response.data.data.card.fans
    // data.fansd=response.data.data[1].datas
    console.log("@");
    console.log(data.fans)
    // data.showthis=true
  })
  .catch(function (error) { console.log(error); });
  }
  console.log(JSON.stringify(data.fans))
  data.showthis=true
  })

 
// })


// const count = ref(0)
</script>

<style scoped>
.mainimg{
  width:500px;
  
  overflow: hidden;
  margin: 0 auto;
  
  box-shadow: 0 0 5px #011147;
}
.group{
  position: relative;
  
}


.textin{
  font-size: large;
  font-weight:bold;
  position: relative;
  color: white;
}
.textin p{
  margin: 3% auto;
}
.textbox{
  position: absolute;
  bottom: 0;
  /* margin: 0 auto; */
  left: 40%;
}

.text2{
  /* position:absolute; */
  font-size: large;
  font-weight:bold;
  width:500px;
  margin: 0 auto;
  color: white;
}
</style>
