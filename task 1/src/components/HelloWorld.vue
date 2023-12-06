<template>
  <div class="">
    <div class="app__date">
      <input v-model="item.name">
      <input v-model="item.date">
      <input v-model="item.desc">
      <button @click="remove">Delete</button>
    </div>
  </div>
</template>   

<script>  
  export default {
    props: {
      item: Object
    },
    methods:{
      remove(){
        this.$emit('remove', this.item.id)
      }
    }
  }
</script>