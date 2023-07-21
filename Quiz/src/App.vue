<script setup>
import {ref, watch} from "vue"
import q from "./data/Quiz.json"
//import Card from "./components/Card.vue" 
const Quiz = ref(q)
const search = ref("") 
watch(search, ()=>{
  console.log("hello from watch")
  Quiz.value = q.filter(quizes=> quizes.name.toLowerCase().includes(search.value.toLowerCase()))
})
</script>
<template>
  <div class="container">
  <h1>
  Quizes:
  </h1>
  <input v-model.trim ="search" type="text" placeholder="search..."/>
  <header/> 
  <div class="options-container">
  <div class="cards" v-for="quizes in Quiz" :key="quizes.id">
  <img :src="quizes.img" alt="">
  <div class="card-text"> 
  <h2>
  {{quizes.name}}
 </h2>
 <p>{{quizes.questions.length}} questions</p>
 </div>
 </div>
 </div>
 </div>
 </template>
 <style>
 .container{
 max-width: 1000px;
 margin: 0 auto;
}
header{
  margin-top: 30px;
  margin-bottom: 10px;
  display: flex;
  align-items: center;
}
header h1{
  font-weight: bold;
  margin-right: 30px;
}
header input{
  border: none;
  background-color: antiquewhite;
  padding: 10px;
  border-radius: 5px;
}
.options-container{
display: flex;
margin: 20px;
}

/*cards*/
.cards{
  width: 310px;
  overflow: hidden;
  border-radius: 2%;
  box-shadow: 1px 1px 10px black;
  margin-bottom: 35px;
  margin-right: 20px;
  cursor: pointer;
}
.card img{
  width:100%;
  height:190px;
  margin: 0;
}
.card .card-text h2{
  padding: 0 5 px;
  font-weight: bold;
}
</style>