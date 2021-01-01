<template>
  <div class="home">
    <h1>Home</h1>
    <HelloWorld msg="Welcome to Your Vue.js App">
      <template v-slot:about='username'>
        <About></About>
        {{username.user}}
      </template>
      <template slot='h1'>
        <h1>h1插槽</h1>
      </template>
      <template v-slot='users'>h2 未被包裹的元素h2 {{users.user}}</template>
    </HelloWorld>
  </div>
</template>
s
<script>
import HelloWorld from '@/components/HelloWorld.vue'
import About from '@/views/About.vue'

export default {
  name: 'Home',
  data(){
    return {
      date:new Date()
    }
  },
  components: {
    HelloWorld,
    About
  }
}
</script>
