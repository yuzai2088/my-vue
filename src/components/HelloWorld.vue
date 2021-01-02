<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <slot :user='user' name='about'>slot--暂无数据！</slot>
    <slot name='h1'>slot--暂无数据！</slot>
    <slot :user='user'></slot>
    <h1 @click='handelparent'>访问根实例</h1>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  injec:['provideee'],
  props: {
    msg: String
  },
  data(){
    return {
      user:'yc'
    }
  },
    methods:{
    handelparent(){
      console.log('hello 组件方法',this.$parent.date)
      console.log('接受父组件的注入参数',this.provideee)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.hello{
  width: 400px;
  height: 400px;
  background: pink;
  margin: 0 auto;
}
</style>
