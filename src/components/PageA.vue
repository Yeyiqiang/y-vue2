<template>
  <div>
    <h4>{{name}}</h4>
    <hr />
    <page-b :msg="msg" :list="list"></page-b>
    <hr />
    <page-c ref="pagec"></page-c>
  </div>
</template>

<script>
import PageB from '@/components/PageB'
import PageC from '@/components/PageC'
export default {
  name: 'page-a',
  components: {
    PageB,PageC
  },
  data(){
    return {
      name:'this is page A',
      msg: 'from A msg',
      list: [
        { name: 'from A list1', id: 1 },
        { name: 'from A list2', id: 2 },
      ],
    }
  },
  mounted(){
    this.changeHomeMsg();// 向C页面传值
  },
  methods: {
    changeMsg(msg) {
      // 绑定接收子组件传过来的值
      this.msg = msg
    },
    changeHomeMsg(){
      // 改变子组件内部值
      this.$refs.pagec.msg = "from A msg"
    }
  },
}
</script>