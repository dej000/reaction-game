<template>
    <div class="backdrop" @click.self ="closeModal">
        <div class="modal">
 
            <h1> {{text}}</h1>
      
            <p>modal component</p>
        </div>
    </div>
</template>

<script>
export default{ 
     props :['text'],
     methods :{
        closeModal(){
            this.$emit('close')
        }
    }
 
}

</script>

<style scoped >
.modal{
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background: white;
    border-radius: 10px;
}

.backdrop{
    top: 0;
    position: fixed;
    background: rgb(0, 0, 0,0.5);
    width :100%;
    height: 100%;
}

p{
    color: black;
}
</style>