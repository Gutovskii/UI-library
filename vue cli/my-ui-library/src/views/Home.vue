<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js + TypeScript App"/>

    <!-- Примеры кнопки -->
    <MyButton color="danger" size="large" @btn-click="hello">Petya</MyButton>
    <MyButton color="warning" size="medium" textColor="black">Vasya</MyButton>
    <MyButton color="info" size="small"></MyButton>
    <MyButton color="success" size="large" @btn-click="hello">Grisha</MyButton>

    <!-- Примеры сетки -->
    <Row>
    	<Column cols="5"></Column>
    	<Column cols="3"></Column>
    	<Column cols="4"></Column>
    </Row>
    <Row>
    	<Column cols="10">10</Column>
    	<Column cols="2"></Column>
    </Row>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src
import MyButton from '@/components/MyButton.vue';
import Row from '@/components/grid/Row.vue';
import Column from '@/components/grid/Column.vue';

export default Vue.extend({
  name: 'Home',
  components: {
    HelloWorld,
    MyButton,
    Row,
    Column,
  },
  methods: {
  	hello(){
  		console.log('hi!');
  	},
  },
});
</script>
