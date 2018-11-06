<template>
    <div class="box">
        <h-input></h-input>   
        <b-bottom></b-bottom> 
    </div>    
</template>

<script>
import hInput from '../hhh/h-input.vue'
import bBottom from '../hhh/b-bottom.vue'
export default {
    name:'divHeader',
    components: {
        hInput,
        bBottom
    }
}
</script>

<style>
.box{
    width: 300px;
    height: 300px;
    border: 1px solid #dedede;
}
</style>

