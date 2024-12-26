<template>
  <div class="layer">
  <lay-carousel v-model="active1">
    <lay-carousel-item v-for="(item,index) in itemList" :id=index>
      <div :style="{'color': 'white','text-align': 'center','width':'100%','height':'300px','line-height':'300px','background-color': item.backgroundColor}">{{item.name}}</div>
    </lay-carousel-item>
  </lay-carousel>
  <lay-slider v-model="number"></lay-slider>
  <lay-input-number v-model="number"></lay-input-number>
  <LayButton :disabled="flag" type="primary" @click="clickButton">点击</LayButton>
    
</div>

</template>



<script setup >
import { ref } from 'vue'

const active1 = ref("1")

let itemList = ref([
  {
    id: 1,
    backgroundColor:"#009688",
    name: '条目一'
  },
  {
    id: 2,
    backgroundColor:"#5FB878",
    name: '条目二'
  },
  {
    id: 3,
    backgroundColor:"#FFB800",
    name: '条目三'
  },
  {
    id: 4,
    backgroundColor:"#FF5722",
    name: '条目四'
  }
])
let number = ref(10)

    function clickButton(){
      number.value +=1
    }

</script>

<style scoped>

.layer{

  width: 800px;
  margin: auto;

}
</style>
