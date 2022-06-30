

<template>
  <h1> Reaction Timer</h1>
  <button @click="start"  :disabled = "isPlaying">play </button>
  <Block v-if="isPlaying"   :delay="delay"  @end = "endGame" />
  <Result v-if="showResults" :score ="score"/>
  
 </template>



<script >
import Block from './components/Block.vue'
import Result from './components/Result.vue'

  export default{
    data(){
      return{
        isPlaying : false ,
        delay : null,
        score : null,
         showResults : false
      }
    },
    components :{Block,Result},
    methods :{
      start(){
        this.delay = 2000 + Math.random() * 5000
        this.isPlaying = true
        this.showResults = false
      },
      endGame(reactionTime){
       this.score =  reactionTime
       this.isPlaying =false
       this.showResults = true 
      }
    }
  }

</script>


<style >
#app {
  font-family: Arial, Helvetica, sans-serif;
  text-align: center;
  color: #444;
  margin-top: 60px;

}
</style>
