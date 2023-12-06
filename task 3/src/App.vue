<template>
  <body>
    <div class="container">
      <div class="carousel">
        <h1>Choose your favourite car</h1>
        <Carousel @next="next" @prev="prev">
          <CarouselSlide class="carousel__slide" v-for="(slide,index) in slides" 
          :key="slide"
          :index="index"
          :visibleSlide="visibleSlide">
            <img :src="slide" />
          </CarouselSlide>
        </Carousel>
      </div>
    </div>
  </body>
</template>

<script>
import Carousel from './components/HelloWorld.vue';
import CarouselSlide from './components/Carousel.vue';

export default{
  data(){
    return{
      slides: [
        '/src/components/assets/2021_audi_a8_sedan_l_fq_oem_1_1600.avif',
        '/src/components/assets/2021-Mercedes-AMG-E63-S-sedan-silver-1001x565-1.webp',
        '/src/components/assets/20201224-ART_1447-flat.jpg',
        '/src/components/assets/cattouchret.webp',
        '/src/components/assets/scale_1200.jpg'
      ],  
      visibleSlide: 0
    }
  },
  methods:{
    next(){
      if(this.visibleSlide >= this.slides.length - 1){
        this.visibleSlide = 0;
      }
      else{
        this.visibleSlide ++;
      }
    },
    prev(){
      if(this.visibleSlide <= 0){
        this.visibleSlide = this.slides.length - 1;
      }
      else{
        this.visibleSlide --;
      }
    }
  },
  components:{
    Carousel,
    CarouselSlide
}
}
</script>

<style>
  *{
    margin: 0;
    padding: 0;
  }
  .container{
    padding: 20px 40px;
  }
  .carousel{
    display: grid;
    justify-content: center;
    justify-items: center;
  }
  .carousel h1{
    padding-bottom: 30px ;
  }
  .carousel__slide img{
    width: 600px;
  }
</style>
