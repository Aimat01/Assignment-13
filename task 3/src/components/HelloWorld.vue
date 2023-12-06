<template>
    <div class="carousel">
        <slot></slot>
        <button @click="next" class="next">Next</button>
        <button @click="prev" class="prev">Prev</button>
    </div>
</template>

<script>
    export default{
        data(){
            return{

            }
        },
        methods:{
            next(){
                this.$emit('next')
            },
            prev(){
                this.$emit('prev')
            }            
        }
    }
</script>

<style>
    button{
        padding: 10px 15px;
    }
    button:focus, button:hover{
        outline: none;
        cursor: pointer;
    }
    .next{
        position: absolute;
        right:  20%;
        top: 38%;
    }
    .prev{
        position: absolute;
        left: 20%;
        top: 38%;
    }
</style>
