
<template>
  <body>
    <div class="container">
      <div class="timeline">
         <app-timeline class="timeline__body" v-for="name in items" :item = name @remove="remove">
         </app-timeline>
      </div>
      <div class="timeline__button">
        <button @click="Add">Add TimeLine</button>
      </div>
    </div>
  </body>
</template>

<script>
import TimeLine from './components/HelloWorld.vue'

export default{
  data(){
    return{
      name: 'Write Name',
      date: 'Write Date',
      desc: 'Write Description',
      id: 0,
      items: [
        {id: this.id, date:'16 February' , name: 'Aimats Birthday' , desc:'Future Millionaire'}
      ]
    }
  },
  methods:{
    Add(){
      this.items.push({
        id:this.id++,
        name:this.name,
        date:this.date,
        desc:this.desc
      })
    },
    remove(index){
      console.log("dsf");
      this.items = this.items.filter((t) => t.id != index)
    }
  } , 
  components: {
    'app-timeline': TimeLine 
  }
}
</script>

<style>
  *{
    margin: 0;
    padding: 0;
  }
  .container{
    padding: 50px 20vh;
  }
  .timeline{
    display: grid;
    grid-template-rows: auto;
    grid-template-columns: 150px 150px 150px;
    justify-content: space-around;
  }
  .timeline__body{
    display: grid;
    align-items: center;
    justify-items: center;
    justify-content: center;
    border: 1px solid;
    padding: 30px 10vh;
    margin-bottom: 50px;
  }
  .timeline__body input{
    border: none;
    outline: none;
    background-color: #181818;
    color: whitesmoke;
    width: 100px;
    text-decoration: underline;
  }
  .timeline__body button{
    margin-top: 40px;
    padding: 5px;
  }
  .timeline__button{
    display: flex;
    justify-content: center;
    align-items: center;
  } 
  .timeline__button button{
    padding: 10px 15px;
  }
</style>
