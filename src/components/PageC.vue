<template>
  <div>
    <div>{{name}}</div>
    <div>来自A页面的值：{{msg}}</div>
  </div>
</template>

<script>
export default {
  name: 'page-c',
  data(){
    return {
      name:'this is page C',
      msg:''
    }
  },
}
</script>