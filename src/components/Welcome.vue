<script setup>
import {ref} from "vue";

const count = ref(7);
const isTitle = ref(true)

//this function changes the isTitle varible to true or false
function changeTitle(){
  isTitle.value = !isTitle.value;
}
//this function is tied to the double click
function addByTwo(){
 count.value+=2
}
//this function is tied to the double click
function minusByTwo(){
  count.value-=2
}

</script>

<template>
  <main>
    <div>
      <h4>The current count is...</h4>
      <h1 :class="isTitle ? 'title' : 'notTitle'">{{count}}</h1>
      <button @dblclick= minusByTwo> minus by 2</button>
      <button @click = "count--">-</button>
      <button @click = "count++" >+</button>
      <button @dblclick= addByTwo> add by 2</button>
      <br>
      <button @click="changeTitle">change color</button>
    </div>
  </main>
</template>

<style scoped>

.title{
  color: red;
}
.notTitle{
  color: green;
}

div{
  text-align: center;
}
</style>