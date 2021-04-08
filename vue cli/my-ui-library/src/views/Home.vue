<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js + TypeScript App"/>
    <MyButton color="danger" size="large" @btn-event="hi">Hello</MyButton>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src
import MyButton from '@/components/MyButton.vue';

export default Vue.extend({
  name: 'Home',
  components: {
    HelloWorld,
    MyButton,
  },
  methods: {
  	hi(){
  		console.log('hello');
  	},
  },
});
</script>
