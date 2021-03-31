<template>
  
 
    <div class="app">
    <v-app>
    <v-main>
      <Stepper/>
    </v-main>
  </v-app>
        <carousel >
            <carousel-slide v-for="slide in slides" :key="slide" class="carousel-slider">
                <img :src="slide" :alt="slide">
            </carousel-slide>
        </carousel>
    </div>    


</template>

<script>

import Stepper from './components/Stepper.vue'
import Carousel from './components/Carousel.vue'
import CarouselSlide from './components/CarouselSlide.vue'
import car1 from './components/carousel 1.jpg'
import car2 from './components/carousel 2.jpg'
import car3 from './components/carousel 3.jpg'

export default {
  name: 'App',

  components: {
    Stepper,
    CarouselSlide,
    Carousel
  },

  data(){
        return {
            slides: [
                   car1,
                   car2,
                   car3,
            ]
        }
    },
};
</script>

<style>
    .app {
        
        justify-content: center;
    }
    .carousel {
        position: relative;
        overflow: hidden;
        width:100%;
        height: 500px;
        z-index:10;
    }
    .btn {
        padding:5px 10px;
        background-color:rgba(0,0,0,0.5);
        border:1px solid transparent;
        border-radius: 50px;
        margin:5px 10px;
        color:#FFF;
        opacity: 0.6;
        height:50px;
        width:50px;
        position:absolute;
        margin-top:-25px;
        z-index:2;
        
    }
    .btn:hover {
        cursor: pointer;
    }
    .btn:focus{
        outline:none;
    }
    .btn-next {
        top:50%;
        right:0;
    }
    .btn-prev {
        top:50%;
        left:0;
    }
    .carousel-slider {
        position:absolute;
        top:0;
        left:0;
        bottom:0;
        right:0;
    }
    .carousel-slider img {
        width:100%;
        height:100%;        
    }
</style>
