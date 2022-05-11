<template>
  <div>
    <div>{{name}}</div>
    <div>来自A页面的值：{{msg}}</div>
    <ul>
      <li v-for="item in list" :key="item.id">
        {{ item.name }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'page-b',
  data(){
    return {
      name:'this is page B'
    }
  },
  props: {
    msg: String,// 接收父组件的值
    list: {
      type: Array, // 类型
      default: ()=>[], /* 默认值为空数组或者空对象需要用到return */
    }
  },
}
</script>