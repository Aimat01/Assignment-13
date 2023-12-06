<template>
  <body>
    <div class="container">
      <div class="accordion">
        <h1>Accordion</h1>
        <Accordion v-for="(item, index) in items" class="accordion__body" :item="item" :index="index" />
      </div>
    </div>
  </body>
</template>

<script>
  import Accordion from './components/HelloWorld.vue'

  export default{
    data(){
      return{
        items: [
          {
            question: "Who is The Best Football player in The World?",
            answer: "Cristiano Ronaldo and Lionel Messi"
          },
          {
            question: "Cheating is the best team",
            answer: "100% information"
          },
          {
            question: "Do you love listening phonk music?",
            answer: "METAMORPHOSIS, LOST ORION, KEROSENE"
          },
          {
            question: "You need to hire some companies",
            answer: "Like Google, Facebook, Apple"
          }
        ]
      }
    },
    components:{
      Accordion
    }
  }
</script>

<style>
  *{
    margin: 0;
    padding: 0;
  }
  .container{
    padding: 30px;
    padding-left: 60px;
    padding-right: 60px;
  }
  .accordion{
    display: grid;
  }
  .accordion h1{
    display: flex;
    justify-content: center;
    padding-bottom: 30px;
  }
  .accordion__body{
    width: 100%;
    max-width: 768px;
    margin: 10px auto;
    padding: 10px;
    border-radius: 8px;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.3);
  }
</style>
