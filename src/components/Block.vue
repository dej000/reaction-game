<template>
  <div class="block" v-if="showblock"  @click = "stop" >
    click me
  </div>
</template>

<script>
export default {
 props : ['delay'],
 data(){
  return{
    showblock : false,
    timer:null,
    reactionTime : 0
  }
 },
 mounted(){
  
  setTimeout(()=> {
    this.showblock = true
    this.start()

  },this.delay)
 }, 

 methods : {
  start(){
    this.timer = setInterval(()=>{
      this.reactionTime += 10
    }, 10)
  },
  stop(){
     clearInterval(this.timer)
     this.$emit('end',this.reactionTime)
  }
 }

}
</script>

<style>
.block{
    width : 400px;
    border-radius: 20px;
    background: crimson;
    color: azure;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
}
</style>