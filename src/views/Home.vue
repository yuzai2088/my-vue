<template>
  <div class="home">
    <h1>Home</h1>
    <button @click="show = !show"  >toggle</button>
    <transition name="moved">
      <HelloWorld v-if="show" ref='hello' msg="Welcome to Your Vue.js App">
        <template v-slot:about='username'>
          <About></About>
          {{username.user}}
        </template>
        <template slot='h1'>
          <h1>h1插槽</h1>
        </template>
        <template v-slot='users'>h2 未被包裹的元素h2 {{users.user}}</template>
      </HelloWorld>
    </transition>
    <h1 @click='handelroot'>访问子实例</h1>
  </div>
</template>
s
<script>
import HelloWorld from '@/components/HelloWorld.vue'
import About from '@/views/About.vue'

export default {
  name: 'Home',
    provide:{
        provideee:'父组件注入参数'
      },
  data(){
    return {
      date:new Date(),
      show:true
    }
  },
  components: {
    HelloWorld,
    About
  },
  methods:{
    handelroot(){
      console.log(this.$refs.hello.handelparent)
      this.$refs.hello.handelparent()
    }
  },
}
</script>

<style>
  .moved-enter-active, .moved-leave-active {
    transition:all 1s ease;
    opacity: 1;
    position: relative;
    left: 0;
  }

  .moved-enter {
    opacity: 0;
    position: relative;
    left: -200px
  }

    .moved-leave-to {
    opacity: 0;
    position: relative;
    left: 500px
  }


  /* .moved-enter-to {
    transition:all 1s ease;
    position: relative;
    top:-20px
  } */

  

  /* .moved-leave {
    position: relative;
    left:-100px;
  } */



</style>

