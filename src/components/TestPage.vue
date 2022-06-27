<template>
  <div>
    <transition-group tag="ul" name="slide" type="animation">
      <li v-for="item in items" :key="item.id">
        {{item.id}}: {{ item.text }}
      </li>
    </transition-group>
    <!-- <div @click="reload()">开始</div> -->
  </div>
</template>

<script>
export default {
  name: 'test-page',
  data(){
    return {
      items:[]
    }
  },
  mounted(){
    this.init()
  },
  methods: {
    randomNum(min = 1000,max=5000){ 
      return Math.floor(Math.random() * (max - min + 1)) + min;
    },
    timer(){
      setInterval(()=>{
        this.reload()
      },5000)
    },
    init(){
      let newItem = [...Array(10).keys()].map((key,i)=>{
        return {id:i,text:this.randomNum()}
      });
      this.items = newItem
      this.timer()
    },
    reload(){
      // let numLen = this.randomNum(1,10);
      let newItem = [...Array(10).keys()].map((key,i)=>{
        return {id:i,text:this.randomNum()}
      });
      this.items = newItem;
    }
  },
}
</script>
<style>

</style>