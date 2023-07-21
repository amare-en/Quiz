<script setup>
import {defineProps} from "vue"
const {quiz} = defineProps(["quiz"])
console.log(quiz)
</script>
<template>
   <div class="cards">
   <img :src="quiz.img">
   <div class="card-text">
       <h1>
     {{quiz.name}}
       </h1>
    </div>
    </div>
</template>
<style scoped>
.cards{
    width: 310px;
    overflow: hidden;
    border-radius: 2%;
    box-shadow: 1px 1px 10px black;
    margin-bottom: 35px;
    margin-right: 20px;
    cursor: pointer;
  }
</style>