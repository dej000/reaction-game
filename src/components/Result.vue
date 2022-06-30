<template>
  <p>Reaction time - {{score}} ms</p>
  <p class="rank">{{rank}}</p>
</template>

<script>
export default {
props :[ 'score'],

data(){
    return{
        rank : null
    }
},
mounted(){
    if(this.score < 250){
        this.rank = 'GOD SPEED'
    }else if(this.score < 400){
        this.rank = 'RAPID REFLEX'
    }else{
        this.rank = 'SNAIL PACE.... '
    }
}
}
</script>

<style>
   .rank{
    font-size: 1.4em;
    color: crimson;
    font-weight: bolder;

}

button{
    background: crimson;
    color: azure;
    border: none;
    padding: 8px 16px;
    border-radius: 4px;
    font-size: 16px;
    letter-spacing: 1px;
    cursor: pointer;
    margin: 10px;
}

button[disabled]{
    opacity: 0.2;
    cursor: not-allowed;
}
</style>